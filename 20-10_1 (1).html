<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no">
<title>20/10 Vui Vẻ</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent;user-select:none}
html,body{height:100%;overflow:hidden;background:#05010f;font-family:"Segoe UI",Roboto,Arial,sans-serif;color:#fff}
canvas{position:fixed;inset:0;width:100%;height:100%;display:block}
.ui{position:fixed;opacity:0;pointer-events:none;transition:opacity .6s}
.ui.on{opacity:1;pointer-events:auto}
#go{background:#ffb3b3;color:#000;border:0;border-radius:12px;padding:10px 24px;font:600 17px inherit;font-family:inherit;box-shadow:0 0 18px rgba(255,150,150,.5)}
#go:active,#back:active{transform:scale(.94)}
#back{top:14px;left:14px;background:rgba(255,255,255,.14);color:#fff;border:1px solid rgba(255,255,255,.3);border-radius:20px;padding:8px 16px;font:600 15px inherit;font-family:inherit}
#mute{top:14px;right:14px;width:40px;height:40px;border-radius:50%;background:rgba(255,255,255,.12);border:1px solid rgba(255,255,255,.25);color:#fff;font-size:18px;opacity:1;pointer-events:auto}
#hint{left:0;right:0;bottom:7%;text-align:center;font-size:16px;letter-spacing:.5px;color:#d9c8ff;animation:pl 1.8s infinite}
@keyframes pl{50%{opacity:.35}}
#info{left:0;right:0;bottom:6%;text-align:center;padding:0 20px}
#info b{display:block;font-size:30px;margin-bottom:6px}
#info span{font-size:15px;color:#e5dcff}
</style>
</head>
<body>
<canvas id="c"></canvas>
<div id="hint" class="ui on">✨ Chạm vào màn hình ✨</div>
<button id="go" class="ui">Tiếp tục</button>
<button id="back" class="ui">‹ Quay lại</button>
<div id="info" class="ui"><b id="nm"></b><span id="ft"></span></div>
<button id="mute" class="ui">🔊</button>
<script>
const cv=document.getElementById('c'),g=cv.getContext('2d');
const $=id=>document.getElementById(id);
let W,H,DPR,R,tilt,cx,cy,bg,stars=[],streaks=[];
const TAU=Math.PI*2,rnd=(a,b)=>a+Math.random()*(b-a);
const ease=t=>t<.5?4*t*t*t:1-Math.pow(-2*t+2,3)/2, sm=(a,b,x)=>{x=Math.min(1,Math.max(0,(x-a)/(b-a)));return x*x*(3-2*x)};

/* ================= ÂM THANH ================= */
let A=null,master,verb,muted=false,noiseBuf;
function initAudio(){
  if(A){A.resume&&A.resume();return}
  try{A=new (window.AudioContext||window.webkitAudioContext)()}catch(e){return}
  master=A.createGain();master.gain.value=.8;
  const comp=A.createDynamicsCompressor();master.connect(comp);comp.connect(A.destination);
  const len=A.sampleRate*2.5,ir=A.createBuffer(2,len,A.sampleRate);
  for(let c=0;c<2;c++){const d=ir.getChannelData(c);for(let i=0;i<len;i++)d[i]=(Math.random()*2-1)*Math.pow(1-i/len,2.6)}
  verb=A.createConvolver();verb.buffer=ir;const vg=A.createGain();vg.gain.value=.55;verb.connect(vg);vg.connect(master);
  noiseBuf=A.createBuffer(1,A.sampleRate*2,A.sampleRate);
  const nd=noiseBuf.getChannelData(0);for(let i=0;i<nd.length;i++)nd[i]=Math.random()*2-1;
  startMusic();
}
const mf=n=>440*Math.pow(2,(n-69)/12);
const chords=[[48,55,59,64,67],[45,52,57,60,64],[41,48,53,57,60],[43,50,55,59,62]];
let ci=0,nextT=0,step=0;
function startMusic(){nextT=A.currentTime+.1;setInterval(sched,250);sched()}
function sched(){
  if(!A||A.state!=='running')return;
  while(nextT<A.currentTime+1){
    const ch=chords[ci%4],t=nextT;
    if(step%8===0){ // pad
      ch.forEach(n=>{[-4,4].forEach(dt=>{
        const o=A.createOscillator(),gn=A.createGain(),f=A.createBiquadFilter();
        o.type='triangle';o.frequency.value=mf(n);o.detune.value=dt;f.type='lowpass';f.frequency.value=900;
        gn.gain.setValueAtTime(0,t);gn.gain.linearRampToValueAtTime(.035,t+1.6);gn.gain.linearRampToValueAtTime(0,t+4.6);
        o.connect(f);f.connect(gn);gn.connect(master);gn.connect(verb);o.start(t);o.stop(t+4.8)})});
    }
    const pat=[0,2,4,2,3,1,4,2];
    const n=ch[pat[step%8]]+12+(step%8===4?12:0);
    bell(mf(n),t,.07,master,verb);
    step++;if(step%8===0)ci++;
    nextT+=.5;
  }
}
function bell(f,t,v,out,out2){
  [1,2.01].forEach((m,i)=>{const o=A.createOscillator(),gn=A.createGain();
    o.type='sine';o.frequency.value=f*m;
    gn.gain.setValueAtTime(0,t);gn.gain.linearRampToValueAtTime(v/(i+1),t+.01);gn.gain.exponentialRampToValueAtTime(.0001,t+1.6);
    o.connect(gn);gn.connect(out);if(out2)gn.connect(out2);o.start(t);o.stop(t+1.7)});
}
function click(){ if(!A)return;const t=A.currentTime;
  const o=A.createOscillator(),o2=A.createOscillator(),gn=A.createGain();
  o.type='sine';o.frequency.setValueAtTime(700,t);o.frequency.exponentialRampToValueAtTime(1400,t+.07);
  o2.type='triangle';o2.frequency.setValueAtTime(1050,t+.05);o2.frequency.exponentialRampToValueAtTime(2100,t+.12);
  gn.gain.setValueAtTime(0,t);gn.gain.linearRampToValueAtTime(.3,t+.005);gn.gain.exponentialRampToValueAtTime(.001,t+.25);
  o.connect(gn);o2.connect(gn);gn.connect(master);gn.connect(verb);o.start(t);o2.start(t);o.stop(t+.3);o2.stop(t+.3)}
function whoosh(rev){ if(!A)return;const t=A.currentTime,d=1.3;
  const s=A.createBufferSource(),f=A.createBiquadFilter(),gn=A.createGain();
  s.buffer=noiseBuf;f.type='bandpass';f.Q.value=.9;
  const a=rev?5000:300,b=rev?300:5000;
  f.frequency.setValueAtTime(a,t);f.frequency.exponentialRampToValueAtTime(b,t+d);
  gn.gain.setValueAtTime(0,t);gn.gain.linearRampToValueAtTime(.9,t+d*.35);gn.gain.linearRampToValueAtTime(0,t+d);
  s.connect(f);f.connect(gn);gn.connect(master);s.start(t);s.stop(t+d+.1);
  const o=A.createOscillator(),og=A.createGain();o.type='sine';
  o.frequency.setValueAtTime(rev?500:90,t);o.frequency.exponentialRampToValueAtTime(rev?90:500,t+d);
  og.gain.setValueAtTime(0,t);og.gain.linearRampToValueAtTime(.12,t+d*.4);og.gain.linearRampToValueAtTime(0,t+d);
  o.connect(og);og.connect(master);o.start(t);o.stop(t+d+.1)}
function sparkle(){ if(!A)return;const t=A.currentTime;[72,76,79,84,88].forEach((n,i)=>bell(mf(n),t+i*.09,.1,master,verb))}
$('mute').onclick=e=>{e.stopPropagation();muted=!muted;$('mute').textContent=muted?'🔇':'🔊';if(master)master.gain.value=muted?0:.8;click()};
document.addEventListener('visibilitychange',()=>{if(!A)return;document.hidden?A.suspend():A.resume()});

/* ================= NỀN ================= */
function resize(){
  DPR=Math.min(window.devicePixelRatio||1,2);W=innerWidth;H=innerHeight;
  cv.width=W*DPR;cv.height=H*DPR;g.setTransform(DPR,0,0,DPR,0,0);
  tilt=W>H?.5:.7;R=Math.min(W*.46,H*.46/tilt);cx=W/2;cy=H*.5;
  // nền tĩnh
  bg=document.createElement('canvas');bg.width=W;bg.height=H;const b=bg.getContext('2d');
  let gr=b.createRadialGradient(W*.5,H*.45,0,W*.5,H*.5,Math.max(W,H)*.8);
  gr.addColorStop(0,'#2b1054');gr.addColorStop(.5,'#12062c');gr.addColorStop(1,'#040010');
  b.fillStyle=gr;b.fillRect(0,0,W,H);
  [[.2,.25,'#7b2cbf'],[.8,.7,'#c026d3'],[.7,.2,'#3b2dbd'],[.25,.8,'#6d28d9']].forEach(([x,y,c])=>{
    const r=Math.max(W,H)*.4,n=b.createRadialGradient(W*x,H*y,0,W*x,H*y,r);
    n.addColorStop(0,c+'55');n.addColorStop(1,c+'00');b.fillStyle=n;b.fillRect(0,0,W,H)});
  b.fillStyle='#fff';// dải ngân hà
  for(let i=0;i<900;i++){const u=rnd(-1,1)*Math.max(W,H)*.75,v=(Math.random()+Math.random()+Math.random()-1.5)*Math.min(W,H)*.22;
    const x=W/2+u*.85-v*.5,y=H/2-u*.5+v*.9;b.globalAlpha=rnd(.1,.5);b.fillRect(x,y,rnd(.5,1.4),rnd(.5,1.4))}
  stars=[];for(let i=0;i<Math.floor(W*H/2600);i++)stars.push({x:Math.random()*W,y:Math.random()*H,r:rnd(.4,1.5),p:rnd(0,TAU),s:rnd(.8,3)});
  streaks=[];for(let i=0;i<150;i++)streaks.push({a:rnd(0,TAU),d:rnd(.1,1)*Math.hypot(W,H)*.6,k:rnd(.6,1.4)});
  layoutText();
  if(scene==='solar'&&!focus)hideEl('info');
}
function drawBG(t,zoom){
  g.globalAlpha=1;g.drawImage(bg,0,0,W,H);g.fillStyle='#fff';
  for(const s of stars){g.globalAlpha=.35+.65*Math.abs(Math.sin(t*s.s+s.p));g.fillRect(s.x,s.y,s.r,s.r)}
  g.globalAlpha=1;
}

/* ================= CHỮ ================= */
const LINES=['20/10','Vui Vẻ','Dành Tặng','12CB1'].map(s=>s.normalize('NFC'));
let glyphs=[],fs=40,blockBottom=0,rightX=0;
function layoutText(){
  fs=Math.min(H*.12,W*.8/5.4,W*.12*(W>H?.5:1)+60);fs=Math.min(fs,W>H?H*.13:W*.15);
  g.font=`800 ${fs}px "Segoe UI",Roboto,Arial,sans-serif`;
  while(Math.max(...LINES.map(l=>g.measureText(l).width))>W*.85)fs--,g.font=`800 ${fs}px "Segoe UI",Roboto,Arial,sans-serif`;
  const lh=fs*1.2,m=W*.06;rightX=W-m;const y0=H*.34;glyphs=[];
  LINES.forEach((ln,li)=>{const lw=g.measureText(ln).width,x0=rightX-lw;
    [...ln].forEach((ch,i)=>{if(ch===' ')return;
      const pre=g.measureText([...ln].slice(0,i).join('')).width,cw=g.measureText(ch).width;
      glyphs.push({ch,x:x0+pre+cw/2,y:y0+li*lh})})});
  blockBottom=y0+3*lh+fs*.6;
  const b=$('go');b.style.right=m+'px';b.style.top=(blockBottom+14)+'px';
  $('hint').style.fontSize=Math.max(14,Math.min(18,W/22))+'px';
}

/* ================= CẢNH 1 ================= */
let scene='intro',phase='fly',tPhase=0,letters=[];
const COLORS=['#ffffff','#f5d0fe','#c4b5fd','#a5f3fc','#fbcfe8'];
const sprites={};
function sprite(ch,col){const k=ch+col;if(sprites[k])return sprites[k];
  const c=document.createElement('canvas');c.width=c.height=72;const x=c.getContext('2d');
  x.font='800 52px "Segoe UI",Roboto,Arial,sans-serif';x.textAlign='center';x.textBaseline='middle';
  x.shadowColor=col;x.shadowBlur=10;x.fillStyle=col;x.fillText(ch,36,38);return sprites[k]=c}
function initLetters(){letters=[];
  for(let i=0;i<80;i++)letters.push({ch:String.fromCharCode(65+Math.floor(Math.random()*26)),col:COLORS[i%5],
    rx:rnd(.18,.55),ry:rnd(.15,.5),a:rnd(0,TAU),w:rnd(1.4,3)*(Math.random()<.5?-1:1),ph:rnd(0,TAU),sz:rnd(22,46),rot:rnd(0,TAU),rw:rnd(-3,3),
    tg:i<glyphs.length?glyphs[i]:null})}
function lpos(l,a){return[W/2+Math.cos(a)*l.rx*W*(1+.12*Math.sin(a*2+l.ph)),H/2+Math.sin(a*1.3+l.ph)*l.ry*H]}
function drawLetter(l,x,y,sz,rot,al){g.globalAlpha=al;g.save();g.translate(x,y);g.rotate(rot);const s=sz/52;g.scale(s,s);g.drawImage(sprite(l.ch,l.col),-36,-38);g.restore()}
function drawIntro(t,dt){
  if(phase==='fly'){
    for(const l of letters){l.a+=l.w*dt;l.rot+=l.rw*dt;
      for(let k=3;k>=0;k--){const[x,y]=lpos(l,l.a-Math.sign(l.w)*k*.07);drawLetter(l,x,y,l.sz,l.rot,k?.22/k+.05:.95)}}
    g.globalAlpha=1;return}
  tPhase+=dt;let done=true;
  letters.forEach((l,i)=>{
    if(!l.st){const[x,y]=lpos(l,l.a);l.st={x,y,rot:l.rot}}
    const dly=(l.tg?i*.05:i*.012),d=1.5,u=Math.min(1,Math.max(0,(tPhase-dly)/d)),e=ease(u);
    if(l.tg){
      if(u<1)done=false;
      const sw=Math.sin(Math.PI*e)*(i%2?1:-1)*Math.min(W,H)*.25;
      const x=l.st.x+(l.tg.x-l.st.x)*e+sw*.6,y=l.st.y+(l.tg.y-l.st.y)*e-sw*.4;
      const k=sm(.7,1,u);
      if(k<1)drawLetter(l,x,y,l.sz+(fs*1.0-l.sz)*e,l.st.rot*(1-e),1-k);
      if(k>0){g.globalAlpha=k;g.fillStyle='#fff';g.font=`800 ${fs}px "Segoe UI",Roboto,Arial,sans-serif`;g.textAlign='center';g.textBaseline='middle';g.fillText(l.tg.ch,x,y)}
    }else if(u<1){
      const x=l.st.x+(W*.7-l.st.x)*e,y=l.st.y+(H*.4-l.st.y)*e;
      drawLetter(l,x,y,l.sz*(1-e),l.st.rot+e*6,1-e)}
  });
  g.globalAlpha=1;
  if(done&&phase==='gather'){phase='formed';sparkle();$('go').classList.add('on')}
  if(phase==='formed'||phase==='leaving'){
    const al=phase==='leaving'?1-sm(0,.6,tPhase2):1;tPhase2+=phase==='leaving'?dt:0;
    g.globalAlpha=al;g.fillStyle='#fff';g.font=`800 ${fs}px "Segoe UI",Roboto,Arial,sans-serif`;g.textAlign='center';g.textBaseline='middle';
    g.shadowColor='rgba(200,170,255,.9)';g.shadowBlur=14+4*Math.sin(t*2);
    for(const q of glyphs)g.fillText(q.ch,q.x,q.y);g.shadowBlur=0;g.globalAlpha=1}
}
let tPhase2=0;

/* ================= CẢNH 2: HỆ MẶT TRỜI ================= */
const P=[
 {n:'Mặt Trời',f:'Ngôi sao trung tâm, cung cấp ánh sáng và sự sống',o:0,sz:.1,sp:0,c:'#ffd24a',type:'sun'},
 {n:'Sao Thủy',f:'Hành tinh nhỏ nhất và gần Mặt Trời nhất',o:.16,sz:.022,c:'#a39a92',b:['#8c837b','#b5aca3']},
 {n:'Sao Kim',f:'Hành tinh nóng nhất, bao phủ bởi mây dày',o:.26,sz:.032,c:'#e6c47e',b:['#d9b36a','#f1d9a0']},
 {n:'Trái Đất',f:'Ngôi nhà xanh của chúng ta',o:.37,sz:.034,c:'#2b6fd8',b:['#3a82ec','#1e58b8'],land:'#3fa34d',moon:1},
 {n:'Sao Hỏa',f:'Hành tinh đỏ với những ngọn núi lửa khổng lồ',o:.48,sz:.027,c:'#c4532f',b:['#b3462a','#d9693f']},
 {n:'Sao Mộc',f:'Hành tinh lớn nhất Hệ Mặt Trời',o:.62,sz:.062,c:'#d9b58c',b:['#b98a62','#f0dcc0','#a8744f','#e8c9a0','#c79a70'],spot:1},
 {n:'Sao Thổ',f:'Nổi tiếng với những vành đai tuyệt đẹp',o:.76,sz:.054,c:'#e8d49c',b:['#d4bd82','#f2e4b8','#c9b074'],ring:1},
 {n:'Thiên Vương Tinh',f:'Hành tinh băng giá xoay nghiêng',o:.88,sz:.042,c:'#8fe3e8',b:['#7fd4da','#a6f0f4']},
 {n:'Hải Vương Tinh',f:'Hành tinh xa nhất với những cơn gió dữ dội',o:.98,sz:.04,c:'#3f5fe3',b:['#3552cc','#5a7af2']}
];
P.forEach((p,i)=>{p.ph=rnd(0,TAU);p.sp=p.o?.075/Math.pow(p.o,1.5):0;p.spots=[];for(let k=0;k<7;k++)p.spots.push({u:Math.random(),v:rnd(-.7,.7),r:rnd(.12,.3)})});
let tSol=0,focus=null,tmpR=0;
function orbitPos(p,t){const a=p.ph+t*p.sp;return[cx+Math.cos(a)*p.o*R,cy+Math.sin(a)*p.o*R*tilt,Math.sin(a)]}
function pr(p){return Math.max(p.type==='sun'?16:3.5,p.sz*R)}
function drawBody(p,x,y,r,t,al){
  g.globalAlpha=al;
  if(p.type==='sun'){
    let gl=g.createRadialGradient(x,y,r*.5,x,y,r*3.2);gl.addColorStop(0,'rgba(255,190,60,.55)');gl.addColorStop(1,'rgba(255,120,20,0)');
    g.fillStyle=gl;g.beginPath();g.arc(x,y,r*3.2*(1+.03*Math.sin(t*2)),0,TAU);g.fill();
    gl=g.createRadialGradient(x-r*.2,y-r*.2,r*.1,x,y,r);gl.addColorStop(0,'#fffbe0');gl.addColorStop(.5,'#ffd24a');gl.addColorStop(1,'#ff8a1f');
    g.fillStyle=gl;g.beginPath();g.arc(x,y,r,0,TAU);g.fill();g.globalAlpha=1;return}
  const ang=-.4;
  const ring=(back)=>{if(!p.ring)return;g.save();g.translate(x,y);g.rotate(ang);
    for(let k=0;k<7;k++){g.strokeStyle=k%2?'rgba(230,210,160,.75)':'rgba(190,165,110,.6)';g.lineWidth=Math.max(1,r*.12);
      g.beginPath();g.ellipse(0,0,r*(1.45+k*.14),r*(1.45+k*.14)*.3,0,back?Math.PI:0,back?TAU:Math.PI);g.stroke()}g.restore();g.globalAlpha=al};
  const moon=(back)=>{if(!p.moon)return;const a=t*1.2,s=Math.sin(a);if((s<0)!==back)return;
    const mr=Math.max(1.8,r*.27);g.fillStyle='#cfcfcf';g.beginPath();g.arc(x+Math.cos(a)*r*2.2,y+s*r*2.2*.35,mr,0,TAU);g.fill()};
  ring(true);moon(true);
  g.save();g.beginPath();g.arc(x,y,r,0,TAU);g.clip();g.fillStyle=p.c;g.fillRect(x-r,y-r,2*r,2*r);
  if(r>7){
    if(p.b&&!p.land){const n=p.b.length;for(let i=0;i<n*3;i++){g.fillStyle=p.b[i%n];g.globalAlpha=al*.55;const yy=y-r+(i/(n*3))*2*r;g.fillRect(x-r,yy,2*r,r*2/(n*3)*1.1)}g.globalAlpha=al}
    p.spots.forEach(s=>{const u=((s.u+t*.03*(p.moon?2:1))%1)*2.6-.8;const sx=x+u*r,sy=y+s.v*r;
      g.globalAlpha=al*.7;g.fillStyle=p.land||(p.spot&&s.r>.26?'#b5523a':p.b?p.b[0]:'#777');
      if(p.land||p.spot||!p.b||s.r>.2){g.beginPath();g.ellipse(sx,sy,s.r*r,s.r*r*.7,0,0,TAU);g.fill()}
      if(p.land){g.fillStyle='#fff';g.globalAlpha=al*.35;g.beginPath();g.ellipse(sx+r*.2,sy-r*.3,s.r*r*1.2,s.r*r*.3,0,0,TAU);g.fill()}});
    g.globalAlpha=al}
  const sh=g.createRadialGradient(x-r*.4,y-r*.4,r*.1,x,y,r*1.05);
  sh.addColorStop(0,'rgba(255,255,255,.18)');sh.addColorStop(.45,'rgba(0,0,0,0)');sh.addColorStop(1,'rgba(5,0,20,.8)');
  g.fillStyle=sh;g.fillRect(x-r,y-r,2*r,2*r);g.restore();g.globalAlpha=al;
  if(r>7){g.strokeStyle='rgba(160,200,255,.25)';g.lineWidth=2;g.beginPath();g.arc(x,y,r,0,TAU);g.stroke()}
  moon(false);ring(false);g.globalAlpha=1;
}
function drawSolar(t,dt){
  tSol+=dt;const ap=ease(Math.min(1,tSol/1.8));
  let e=0;
  if(focus){focus.t=Math.min(1,focus.t+dt/2.4);e=ease(focus.dir>0?focus.t:1-focus.t);
    if(focus.dir<0&&focus.t>=1){focus=null;e=0}}
  else e=0;
  const fade=1-e*.92;
  // quỹ đạo
  g.lineWidth=1;g.strokeStyle='rgba(200,180,255,'+(.14*fade*ap)+')';
  P.forEach(p=>{if(!p.o)return;g.beginPath();g.ellipse(cx,cy,p.o*R*ap,p.o*R*tilt*ap,0,0,TAU);g.stroke()});
  const list=P.map(p=>{const[x,y,s]=orbitPos(p,t);return{p,x:cx+(x-cx)*ap,y:cy+(y-cy)*ap,s:p.o?s:0}});
  const rb=p=>{const rr=Math.min(Math.min(W,H)*.3,W*.46/(p.ring?2.2:1));return p.type==='sun'?Math.min(W,H)*.22:rr};
  list.sort((a,b)=>a.s-b.s);
  // thân sau Mặt Trời (s<0) trước, rồi Mặt Trời, rồi trước
  let sunDone=false;
  const draw=o=>{const p=o.p;let x=o.x,y=o.y,r=pr(p)*ap,al=fade*Math.min(1,ap*2);
    if(focus&&focus.p===p){const r1=rb(p),r0=r||1;r=r0*Math.pow(r1/r0,e);const k=ease(Math.min(1,e*1.15));x=x+(W/2-x)*k;y=y+(H*.4-y)*k;al=1}
    p._x=x;p._y=y;p._r=r;drawBody(p,x,y,r,t,al)};
  for(const o of list){if(o.p.type==='sun')continue;if(o.s<0)draw(o)}
  draw(list.find(o=>o.p.type==='sun'));
  for(const o of list){if(o.p.type==='sun')continue;if(o.s>=0)draw(o)}
  if(focus&&focus.dir>0&&focus.t>=1&&!focus.shown){focus.shown=1;$('nm').textContent=focus.p.n;$('ft').textContent=focus.p.f;$('info').classList.add('on');$('back').classList.add('on')}
  // vệt tốc độ
  const u=focus?focus.t:0;let I=focus?Math.min(u/.15,1,(1-u)/.35):0;
  if(warpIn>0)I=Math.max(I,warpIn);
  I=Math.max(0,I);drawStreaks(dt,I);
}
let warpIn=0;
function drawStreaks(dt,I){
  if(I<.02)return;const D=Math.hypot(W,H)*.55;g.lineCap='round';
  for(const s of streaks){
    s.d+=(60+D*1.6*I)*s.k*dt*(.3+s.d/D);if(s.d>D*1.05){s.d=rnd(.08,.3)*D;s.a=rnd(0,TAU)}
    const f=s.d/D,len=s.d*(.1+.55*I)*I,al=Math.min(1,Math.max(0,f-.08)*2.2)*I;
    const c=Math.cos(s.a),sn=Math.sin(s.a);
    g.strokeStyle='rgba(255,255,255,'+al.toFixed(2)+')';g.lineWidth=.6+2.2*f*s.k;
    g.beginPath();g.moveTo(cx+c*(s.d-len),cy+sn*(s.d-len));g.lineTo(cx+c*s.d,cy+sn*s.d);g.stroke()}
}
function hit(x,y){let best=null,bd=1e9;
  for(const p of P){if(p._x==null)continue;const r=Math.max(p._r*(p.ring?2:1)+8,26),d=Math.hypot(x-p._x,y-p._y);
    if(d<r&&d<bd){best=p;bd=d}}return best}
function hideEl(id){$(id).classList.remove('on')}

/* ================= ĐIỀU KHIỂN ================= */
cv.addEventListener('pointerdown',e=>{
  e.preventDefault();initAudio();
  if(scene==='intro'){
    if(phase==='fly'){click();phase='gather';tPhase=0;hideEl('hint');whoosh(false)}
    return}
  if(focus){if(focus.dir>0&&focus.t>=1)goBack();return}
  const p=hit(e.clientX,e.clientY);
  if(p){click();focus={p,t:0,dir:1,shown:0};whoosh(false)}
});
$('go').addEventListener('click',()=>{initAudio();click();hideEl('go');phase='leaving';tPhase2=0;whoosh(false);
  const t0=performance.now();
  (function f(){const k=(performance.now()-t0)/1000;warpIn=Math.min(1,k/.5);
    if(k<.9)requestAnimationFrame(f);else{scene='solar';tSol=0;phase='';
      const t1=performance.now();(function d(){const q=(performance.now()-t1)/1000;warpIn=Math.max(0,1-q/1.2);if(q<1.2)requestAnimationFrame(d);else warpIn=0})();
      $('hint').textContent='Chạm vào hành tinh để bay đến ✨';$('hint').classList.add('on');setTimeout(()=>hideEl('hint'),5000)}})()});
function goBack(){if(!focus||focus.dir<0)return;click();whoosh(true);focus.dir=-1;focus.t=0;hideEl('info');hideEl('back')}
$('back').addEventListener('click',goBack);

/* ================= VÒNG LẶP ================= */
let last=0;
resize();initLetters();
addEventListener('resize',()=>{resize();if(phase==='fly')initLetters()});
function frame(ts){
  const t=ts/1000,dt=Math.min(.05,last?t-last:.016);last=t;
  drawBG(t);
  if(scene==='intro'){drawIntro(t,dt);if(warpIn>0)drawStreaks(dt,warpIn)}
  else drawSolar(t,dt);
  requestAnimationFrame(frame);
}
requestAnimationFrame(frame);
</script>
</body>
</html>
