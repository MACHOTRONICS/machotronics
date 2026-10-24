/* MACHOTRONICS — prapavijë animuese: planet që rrotullohet, unaza që sillen, yje me shpërthime të vogla */
(function(){
var cv=document.createElement('canvas');cv.setAttribute('aria-hidden','true');
cv.style.cssText='position:fixed;inset:0;width:100%;height:100%;z-index:-1;pointer-events:none;display:block';
var st=document.createElement('style');
st.textContent='body{background:#01030a!important;background-image:none!important}body::before,body::after{display:none!important}';
document.head.appendChild(st);document.body.insertBefore(cv,document.body.firstChild);
var ctx=cv.getContext('2d'),reduce=window.matchMedia&&matchMedia('(prefers-reduced-motion: reduce)').matches;
var W,H,DPR,cx,cy,R,PR,bg,pl,plx,imgd,n,U,RW,SH,RM,AL,IX,stars=[],ring=[],bursts=[],nextB=0;

/* ---------- tekstura e planetit (zhurmë procedurale, blu si në foto) ---------- */
var TW=512,TH=256,tex=new Uint8ClampedArray(TW*TH*4);
function hs(x,y){var k=(Math.imul(x,374761393)+Math.imul(y,668265263))|0;k=Math.imul(k^(k>>>13),1274126177);return((k^(k>>>16))>>>0)/4294967295}
function vn(x,y,p){var xi=Math.floor(x),yi=Math.floor(y),fx=x-xi,fy=y-yi;fx=fx*fx*(3-2*fx);fy=fy*fy*(3-2*fy);
 var x0=((xi%p)+p)%p,x1=(x0+1)%p,a=hs(x0,yi),b=hs(x1,yi),c=hs(x0,yi+1),d=hs(x1,yi+1);return a+(b-a)*fx+(c-a)*fy+(a-b-c+d)*fx*fy}
function fbm(x,y,p){var s=0,a=.5;for(var o=0;o<4;o++){s+=a*vn(x,y,p);x*=2;y*=2;p*=2;a*=.5}return s}
function mk(){
 for(var ty=0;ty<TH;ty++)for(var tx=0;tx<TW;tx++){
  var u=tx/TW,v=ty/TH,dx=u-.58;if(dx>.5)dx-=1;if(dx<-.5)dx+=1;var dy=v-.62,d2=dx*dx*4+dy*dy,an=4*Math.exp(-d2*40),c=Math.cos(an),s=Math.sin(an);
  var su=u+(dx*c-dy*s-dx),sv=v+(dx*s+dy*c-dy);
  var w=fbm(su*4+3,sv*10,4),band=Math.sin(sv*Math.PI*9+w*5)*.5+.5,tu=fbm(su*8,sv*20+w*3,8);
  var t=.55*band+.45*tu+.35*Math.exp(-d2*120)-.3*Math.exp(-d2*600);t=Math.max(0,Math.min(1,t));t=t*t*(3-2*t);
  var r,g,b;if(t<.5){var k=t/.5;r=4+21*k;g=12+68*k;b=70+155*k}else{var k2=(t-.5)/.5;r=25+160*k2;g=80+135*k2;b=225+30*k2}
  var i=(ty*TW+tx)*4;tex[i]=r;tex[i+1]=g;tex[i+2]=b;tex[i+3]=255}
}
mk();

/* ---------- sfera: tabela e kërkimit për çdo piksel ---------- */
function buildSphere(){
 var S=PR*2;pl=document.createElement('canvas');pl.width=pl.height=S;plx=pl.getContext('2d');imgd=plx.createImageData(S,S);
 U=new Float32Array(S*S);RW=new Uint32Array(S*S);SH=new Float32Array(S*S);RM=new Float32Array(S*S);AL=new Uint8Array(S*S);IX=new Uint32Array(S*S);n=0;
 for(var y=0;y<S;y++)for(var x=0;x<S;x++){
  var nx=(x+.5-PR)/PR,ny=(y+.5-PR)/PR,r2=nx*nx+ny*ny;if(r2>1)continue;
  var nz=Math.sqrt(1-r2),lon=Math.atan2(nx,nz),lat=Math.asin(-ny),dd=nx*-.55+ny*-.45+nz*.7;
  var row=Math.max(0,Math.min(TH-1,Math.floor((.5-lat/Math.PI)*TH)));
  U[n]=lon/(2*Math.PI);RW[n]=row*TW;SH[n]=.1+.95*Math.max(0,Math.min(1,dd));
  RM[n]=Math.pow(1-nz,3)*(.2+.8*Math.max(0,dd));AL[n]=Math.max(0,Math.min(1,(1-Math.sqrt(r2))*PR))*255;IX[n]=y*S+x;n++}
}
function drawPlanet(rot){
 var d=imgd.data;
 for(var k=0;k<n;k++){
  var tx=((((U[k]+rot)%1)+1)%1*TW)|0,ti=(RW[k]+tx)*4,p=IX[k]*4,sh=SH[k],rm=RM[k];
  d[p]=Math.min(255,tex[ti]*sh+rm*40);d[p+1]=Math.min(255,tex[ti+1]*sh+rm*90);d[p+2]=Math.min(255,tex[ti+2]*sh+rm*160);d[p+3]=AL[k]}
 plx.putImageData(imgd,0,0);ctx.drawImage(pl,cx-R,cy-R,R*2,R*2)
}

/* ---------- fusha e yjeve, mjegullnaja, unazat ---------- */
function rnd(a,b){return a+Math.random()*(b-a)}
function setup(){
 DPR=Math.min(window.devicePixelRatio||1,1.5);W=innerWidth;H=innerHeight;cv.width=W*DPR;cv.height=H*DPR;ctx.setTransform(DPR,0,0,DPR,0,0);
 cx=W*.5;cy=H*.52;R=Math.max(70,Math.min(240,Math.min(W,H)*.2));PR=Math.round(Math.min(R*DPR,180));buildSphere();
 bg=document.createElement('canvas');bg.width=W;bg.height=H;var b=bg.getContext('2d');b.fillStyle='#01030a';b.fillRect(0,0,W,H);
 for(var i=0;i<9;i++){var x=rnd(0,W),y=rnd(0,H),r=rnd(.18,.4)*Math.max(W,H),g=b.createRadialGradient(x,y,0,x,y,r);g.addColorStop(0,'rgba(20,60,210,.16)');g.addColorStop(1,'rgba(20,60,210,0)');b.fillStyle=g;b.fillRect(0,0,W,H)}
 for(i=0;i<700;i++){b.fillStyle='rgba(150,190,255,'+rnd(.15,.7)+')';var s=Math.random()<.9?1:1.6;b.fillRect(rnd(0,W),rnd(0,H),s,s)}
 stars=[];var ns=Math.round(W*H/9000);for(i=0;i<ns;i++)stars.push({x:rnd(0,W),y:rnd(0,H),s:rnd(.8,2),p:rnd(0,6.28),v:rnd(.0006,.0024)});
 ring=[];var cnt=Math.round(Math.max(1400,R*14)),k=0;
 while(k<cnt){var q=rnd(1.35,2.2);if((q>1.62&&q<1.68)||(q>1.92&&q<1.97))continue;
  ring.push({q:q,a:rnd(0,6.283),w:.00026*Math.pow(1.35/q,1.5)*(Math.random()<.5?1:1),z:rnd(.6,1.6),l:rnd(.35,1),c:q<1.62?'110,160,255':q<1.92?'170,205,255':'90,130,240'});k++}
}
var TILT=-.34,CS=Math.cos(TILT),SN=Math.sin(TILT),FLAT=.27;
function drawRing(front,t){
 for(var i=0;i<ring.length;i++){var p=ring[i],a=p.a+p.w*t,sy=Math.sin(a);if((sy>0)!==front)continue;
  var ex=Math.cos(a)*p.q*R,ey=sy*p.q*R*FLAT,x=cx+ex*CS-ey*SN,y=cy+ex*SN+ey*CS,dim=front?1:.7;
  ctx.fillStyle='rgba('+p.c+','+(p.l*dim).toFixed(2)+')';ctx.fillRect(x,y,p.z*1.6,p.z*.8)}
}
function drawStars(t){
 for(var i=0;i<stars.length;i++){var s=stars[i],a=.3+.7*(.5+.5*Math.sin(t*s.v+s.p));ctx.fillStyle='rgba(180,210,255,'+a.toFixed(2)+')';ctx.fillRect(s.x,s.y,s.s,s.s)}
 if(!reduce&&t>nextB){var s2=stars[(Math.random()*stars.length)|0];bursts.push({x:s2.x,y:s2.y,t0:t,d:Array.from({length:7},function(){var an=rnd(0,6.283);return[Math.cos(an),Math.sin(an),rnd(.01,.03)]})});nextB=t+rnd(700,2000)}
 for(i=bursts.length-1;i>=0;i--){var bu=bursts[i],age=t-bu.t0;if(age>1000){bursts.splice(i,1);continue}
  var al=(1-age/1000)*.4;ctx.fillStyle='rgba(190,220,255,'+al.toFixed(2)+')';ctx.fillRect(bu.x-1,bu.y-1,2.5,2.5);
  for(var j=0;j<bu.d.length;j++){var d=bu.d[j];ctx.fillRect(bu.x+d[0]*d[2]*age*6,bu.y+d[1]*d[2]*age*6,1.2,1.2)}}
}
function frame(t){
 ctx.drawImage(bg,0,0,W,H);drawStars(t);
 var g=ctx.createRadialGradient(cx,cy,R*.9,cx,cy,R*1.9);g.addColorStop(0,'rgba(30,80,255,.22)');g.addColorStop(1,'rgba(30,80,255,0)');ctx.fillStyle=g;ctx.fillRect(0,0,W,H);
 drawRing(false,t);drawPlanet(t*.00003);drawRing(true,t)
}
function loop(t){frame(t);requestAnimationFrame(loop)}
setup();
if(reduce)frame(0);else requestAnimationFrame(loop);
var rt;addEventListener('resize',function(){clearTimeout(rt);rt=setTimeout(function(){setup();if(reduce)frame(0)},150)});
})();
