<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>A Little Surprise Just for You</title>
<!-- HOW TO USE: save as index.html and open in a browser. Everything (CSS, JS, 3 photos) is inside this one file.
     EDIT: look for "EDIT" comments and the CONFIG block at the top of the <script>.
     NOTE: the password is checked in the page itself, so it is a visual gate, not real security.
     Fonts load from Google Fonts (needs internet); readable fallbacks are used offline. -->
<link rel="preconnect" href="https://fonts.googleapis.com"><link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Abril+Fatface&family=Cormorant+Garamond:ital,wght@0,500;0,700;1,500&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box}[hidden]{display:none!important}
:root{--cream:#f8f1e4;--ivory:#fffaf0;--blush:#f3c9d1;--rose:#c98291;--burg:#7a1424;--gold:#c8a04a;--ink:#4a1420;
--heart:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24'%3E%3Cpath fill='%23c98291' d='M12 21s-8-5.2-8-11a4.5 4.5 0 0 1 8-2.8A4.5 4.5 0 0 1 20 10c0 5.800-8 11-8 11z'/%3E%3C/svg%3E")}
body{margin:0;min-height:100vh;color:var(--ink);font:500 1.2rem/1.7 'Cormorant Garamond',Georgia,serif;overflow-x:hidden;
background:radial-gradient(900px 600px at 8% 0,#fbdde2,transparent 60%),radial-gradient(800px 600px at 100% 100%,#f6d9c0,transparent 60%),var(--cream)}
body.lock{overflow:hidden}
button{font:inherit;color:inherit;cursor:pointer}
:focus-visible{outline:3px solid var(--burg);outline-offset:3px}
.script{font-family:'Great Vibes','Segoe Script',cursive;color:var(--burg);font-weight:400;line-height:1.15}
.display{font-family:'Abril Fatface','Playfair Display',Georgia,serif;color:var(--burg);letter-spacing:.05em;font-weight:400}
h1,h2{margin:0}h2.script{font-size:clamp(2.2rem,9vw,3.4rem)}
.kick{letter-spacing:.3em;font-size:.8rem;text-transform:uppercase;color:var(--gold);margin:0 0 .3rem;font-weight:700}
.typing::after{content:'|';color:var(--gold);animation:bl .7s steps(1) infinite}@keyframes bl{50%{opacity:0}}
.card{background:rgba(255,250,240,.85);backdrop-filter:blur(8px);border:1px solid rgba(200,160,74,.45);border-radius:22px;box-shadow:0 24px 50px -28px rgba(122,20,36,.55);padding:1.4rem}
.btn{border:1px solid var(--gold);border-radius:999px;padding:.75rem 1.7rem;background:linear-gradient(135deg,#8f1b2f,#640d1b);color:#fff2d6;font-weight:700;position:relative;overflow:hidden;animation:glow 2.6s ease-in-out infinite}
.btn.alt{background:var(--ivory);color:var(--burg)}
.btn::after{content:'';position:absolute;top:0;left:-70%;width:40%;height:100%;background:linear-gradient(100deg,transparent,rgba(255,255,255,.5),transparent);transform:skewX(-20deg);animation:sh 3.4s infinite}
@keyframes sh{0%,55%{left:-70%}100%{left:130%}}
@keyframes glow{0%,100%{box-shadow:0 0 10px rgba(200,160,74,.4),0 8px 22px -10px rgba(122,20,36,.7)}50%{box-shadow:0 0 26px rgba(200,160,74,.85),0 10px 26px -8px rgba(122,20,36,.8)}}
#fx{position:fixed;inset:0;width:100%;height:100%;pointer-events:none;z-index:90}
.fl{position:fixed;inset:0;pointer-events:none;z-index:0;overflow:hidden}.fl span{position:absolute;opacity:0}
.fl .h{bottom:-40px;background:var(--heart) center/contain no-repeat;animation:rise linear infinite}
.fl .p{top:-30px;width:11px;height:15px;border-radius:100% 0 100% 0;background:linear-gradient(135deg,#dd93a2,#8c1a2d);animation:fall linear infinite}
.fl .s{width:9px;height:9px;background:var(--gold);clip-path:polygon(50% 0,62% 38%,100% 50%,62% 62%,50% 100%,38% 62%,0 50%,38% 38%);animation:tw ease-in-out infinite}
@keyframes rise{0%{transform:translateY(0);opacity:0}15%{opacity:.7}100%{transform:translateY(-110vh) translateX(30px);opacity:0}}
@keyframes fall{0%{transform:translate(0,0) rotate(0);opacity:0}10%{opacity:.85}100%{transform:translate(60px,110vh) rotate(540deg);opacity:.2}}
@keyframes tw{0%,100%{opacity:0;transform:scale(.4)}50%{opacity:.95;transform:scale(1.3)}}
.ldr{position:relative;width:140px;height:140px;margin:0 auto .6rem;display:grid;place-items:center}
.ldr::before{content:'';position:absolute;inset:0;border-radius:50%;background:conic-gradient(transparent,#c8a04a,#e8909f,transparent 70%);-webkit-mask:radial-gradient(circle,transparent 66%,#000 67%);mask:radial-gradient(circle,transparent 66%,#000 67%);animation:spin 1.8s linear infinite}
.ldr i{position:absolute;inset:0;animation:spin var(--s) linear infinite}
.ldr i::after{content:'';position:absolute;top:-5px;left:50%;width:10px;height:10px;margin-left:-5px;background:var(--gold);clip-path:polygon(50% 0,62% 38%,100% 50%,62% 62%,50% 100%,38% 62%,0 50%,38% 38%)}
.ldr .bigheart{margin:0;width:78px;height:78px}
.ltrack{height:9px;border-radius:99px;background:rgba(200,160,74,.25);overflow:hidden;margin:1.1rem 0 .4rem;border:1px solid rgba(200,160,74,.5)}
#lbar{height:100%;width:0;border-radius:inherit;background:linear-gradient(90deg,#e8909f,#c8a04a,#f3d58c)}
/* lock */
.lockscr{position:fixed;inset:0;z-index:80;display:grid;place-items:center;padding:1rem;background:radial-gradient(circle at 50% 30%,#fbe3e6,#f1d2c4 70%);transition:opacity .9s,visibility .9s}
