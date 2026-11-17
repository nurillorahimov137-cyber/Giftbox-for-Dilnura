# Giftbox-for-Dilnura
Giftbox
<!DOCTYPE html>
<html lang="uz">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="theme-color" content="#100d24" />
  <meta name="description" content="Dilnura uchun kichik, sehrli sovg'a." />
  <title>Dilnura uchun ✨</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Playfair+Display:wght@500;600;700&display=swap');
    :root { --pink:#ff8fc7; --lav:#b9a4ff; --white:#fff8ff; }
    * { box-sizing:border-box; }
    html,body { margin:0; min-height:100%; }
    body {
      min-height:100vh; overflow-x:hidden; color:var(--white);
      font-family:'DM Sans',sans-serif;
      background:
        radial-gradient(ellipse at 50% 42%, rgba(117,76,174,.30), transparent 42%),
        radial-gradient(ellipse at 15% 15%, rgba(255,115,183,.13), transparent 35%),
        linear-gradient(145deg,#090817,#17102e 55%,#090817);
      display:grid; place-items:center; padding:28px 16px;
    }
    #stars { position:fixed; inset:0; pointer-events:none; overflow:hidden; }
    .star { position:absolute; width:2px; height:2px; border-radius:50%; background:#fff; opacity:.55; animation:twinkle 3s ease-in-out infinite; }
    @keyframes twinkle { 0%,100%{opacity:.18;transform:scale(.7)} 50%{opacity:.9;transform:scale(1.5)} }
    .wrap { width:min(100%,620px); text-align:center; position:relative; z-index:1; }
    .eyebrow { display:inline-flex; align-items:center; gap:8px; padding:8px 14px; border:1px solid #ffffff20; border-radius:99px; background:#ffffff0b; color:#e7d9ff; font-size:12px; letter-spacing:.14em; text-transform:uppercase; }
    .eyebrow i { width:6px;height:6px;border-radius:50%;background:#ff9acb;box-shadow:0 0 12px #ff9acb; }
    h1 { margin:18px 0 8px; font:600 clamp(42px,10vw,68px)/1.05 'Playfair Display',serif; letter-spacing:-.035em; background:linear-gradient(100deg,#fff 15%,#ffc2e0 52%,#c9baff 90%); -webkit-background-clip:text; background-clip:text; color:transparent; text-shadow:0 10px 50px #d88bff22; }
    .intro { margin:0 auto; max-width:440px; color:#d6cde8; line-height:1.7; font-size:15px; }
    .scene { height:300px; display:grid; place-items:center; perspective:900px; margin:8px 0 0; position:relative; }
    .glow { position:absolute; width:230px;height:90px;bottom:45px;border-radius:50%;background:#d65ca8;filter:blur(55px);opacity:.22; }
    .gift { width:156px;height:150px;position:relative;transform-style:preserve-3d; transform:rotateX(-8deg) rotateY(-23deg); transition:transform 1s cubic-bezier(.2,.8,.2,1); filter:drop-shadow(0 25px 25px #0008); }
    .gift:hover { transform:rotateX(-5deg) rotateY(-12deg) translateY(-5px); }
    .box-base { position:absolute; width:150px;height:105px;bottom:0;left:3px; transform-style:preserve-3d; }
    .front { position:absolute; inset:0; background:linear-gradient(135deg,#c94c9d,#873f9e); border:1px solid #ffc5e955; }
    .front:before { content:"";position:absolute;left:62px;top:0;width:25px;height:100%;background:linear-gradient(90deg,#ffd5ed,#ff9acb,#f8c4e5);box-shadow:0 0 18px #ffb5df66; }
    .side { position:absolute; width:45px;height:105px;right:-45px;top:0;transform:skewY(-35deg);transform-origin:left;background:linear-gradient(90deg,#78347f,#50285f); }
    .top { position:absolute; width:150px;height:45px;left:0;top:-45px;transform:skewX(-45deg) translateX(22px);transform-origin:bottom;background:linear-gradient(135deg,#f18ac2,#b64caa); }
    .lid { position:absolute; width:170px;height:35px;left:-7px;top:-52px;transform:translateZ(5px);transform-style:preserve-3d;transition:transform 1s cubic-bezier(.2,.8,.2,1); }
    .lid-top { position:absolute;inset:0;background:linear-gradient(110deg,#ffb2d9,#d76bb8 70%,#a64b9f);border:1px solid #ffe0f377; }
    .lid-top:after { content:"";position:absolute;left:73px;top:0;width:24px;height:100%;background:linear-gradient(90deg,#fff0f8,#ffb5dc,#ffe7f5); }
    .bow { position:absolute;top:-28px;left:67px;width:36px;height:24px; }
    .bow:before,.bow:after { content:"";position:absolute;width:22px;height:19px;border:7px solid #ffe0f1;border-radius:70% 70% 15% 70%;box-shadow:0 0 10px #ffb5dc88; }
    .bow:before { left:-7px;transform:rotate(25deg); }
    .bow:after { right:-7px;transform:scaleX(-1) rotate(25deg); }
    .gift.open { transform:rotateX(-5deg) rotateY(-15deg) translateY(7px); }
    .gift.open .lid { transform:translate3d(-12px,-75px,35px) rotateX(-28deg) rotateZ(-12deg); }
    .gift.open .bow { opacity:.3; }
    .tap-hint { position:absolute;bottom:12px;color:#bcb0d2;font-size:12px;letter-spacing:.04em;animation:pulse 1.8s infinite; }
    @keyframes pulse { 50%{opacity:.45} }
    .open-btn { border:1px solid #ffffff30; color:#fff; background:linear-gradient(110deg,#d65ca8,#8b65d8); padding:14px 25px; border-radius:999px; font:600 14px 'DM Sans'; cursor:pointer; box-shadow:0 10px 35px #a64caa55,inset 0 1px #ffffff55; transition:.25s; }
    .open-btn:hover { transform:translateY(-2px);box-shadow:0 14px 40px #a64caa77; }
    .message { max-height:0;opacity:0;overflow:hidden;transform:translateY(12px);transition:all .8s ease; }
    .message.show { max-height:330px;opacity:1;transform:translateY(0);margin-top:16px; }
    .note { margin:0 auto;max-width:470px;padding:22px 24px;border:1px solid #ffffff24;border-radius:22px;background:linear-gradient(135deg,#ffffff12,#ffffff06);box-shadow:0 20px 60px #0003;backdrop-filter:blur(12px); }
    .note .small-heart { font-size:23px; filter:drop-shadow(0 0 12px #ff8fc7); }
    .note p { margin:10px 0 0;color:#eee5f8;line-height:1.8;font-size:15px; }
    .signature { margin-top:13px;color:#ffb7dc;font:600 18px 'Playfair Display',serif; }
    .footer { margin-top:28px;color:#8e83a7;font-size:11px;letter-spacing:.08em; }
    .particle { position:fixed;z-index:5;pointer-events:none;animation:fly 2.8s ease-out forwards; }
    @keyframes fly { 0%{transform:translate(0,0) scale(.5) rotate(0);opacity:0} 15%{opacity:1} 100%{transform:translate(var(--x),var(--y)) scale(1.25) rotate(var(--r));opacity:0} }
    @media(max-width:420px){.scene{height:270px}.intro{font-size:14px}.note{padding:19px 17px}.note p{font-size:14px}}
    @media(prefers-reduced-motion:reduce){*,*:before,*:after{animation-duration:.01ms!important;transition-duration:.01ms!important}}
  </style>
</head>
<body>
  <div id="stars" aria-hidden="true"></div>
  <main class="wrap">
    <div class="eyebrow"><i></i> kichik bir syurpriz</div>
    <h1>Dilnura</h1>
    <p class="intro">Bugun senga kayfiyatingni ko‘taradigan kichkina, ammo samimiy sovg‘a tayyorladim.</p>

    <section class="scene" aria-label="Sehrli sovg‘a qutisi">
      <div class="glow"></div>
      <div class="gift" id="gift">
        <div class="box-base">
          <div class="front"></div><div class="side"></div><div class="top"></div>
        </div>
        <div class="lid"><div class="lid-top"></div><div class="bow"></div></div>
      </div>
      <div class="tap-hint" id="hint">Sovg‘a qutisini ochish uchun tugmani bos ✨</div>
    </section>

    <button class="open-btn" id="openBtn">Sovg‘ani ochish 💝</button>

    <section class="message" id="message" aria-live="polite">
      <div class="note">
        <div class="small-heart">♡</div>
        <p>Dilnura, har bir kuning chiroyli lahzalar, yoqimli tabassumlar va kutilmagan quvonchlarga boy bo‘lsin. Doimo o‘zingga yarashgan tabassumingni yo‘qotma. Bugun ham, ertaga ham kayfiyating a’lo bo‘lishiga tilakdoshman! 🌷</p>
        <div class="signature">Senga ezgu tilaklar bilan ✨</div>
      </div>
    </section>
    <div class="footer">BU KICHKINA SOVG‘A FAQAT SEN UCHUN</div>
  </main>

  <script>
    const stars = document.getElementById('stars');
    for (let i = 0; i < 85; i++) {
      const s = document.createElement('span');
      s.className = 'star';
      s.style.left = Math.random() * 100 + '%';
      s.style.top = Math.random() * 100 + '%';
      s.style.animationDelay = (Math.random() * 4) + 's';
      s.style.animationDuration = (2 + Math.random() * 3) + 's';
      stars.appendChild(s);
    }

    const gift = document.getElementById('gift');
    const btn = document.getElementById('openBtn');
    const message = document.getElementById('message');
    const hint = document.getElementById('hint');
    let opened = false;

    function burst() {
      const symbols = ['♡', '♥', '✦', '✨', '🌸'];
      for (let i = 0; i < 34; i++) {
        const p = document.createElement('span');
        p.className = 'particle';
        p.textContent = symbols[Math.floor(Math.random() * symbols.length)];
        p.style.left = (window.innerWidth / 2 + (Math.random() - .5) * 100) + 'px';
        p.style.top = (window.innerHeight * .48 + (Math.random() - .5) * 50) + 'px';
        p.style.color = ['#ff9bcf', '#d6baff', '#fff0fa', '#ffc66e'][i % 4];
        p.style.fontSize = (14 + Math.random() * 20) + 'px';
        p.style.setProperty('--x', ((Math.random() - .5) * 500) + 'px');
        p.style.setProperty('--y', (-100 - Math.random() * 330) + 'px');
        p.style.setProperty('--r', ((Math.random() - .5) * 180) + 'deg');
        document.body.appendChild(p);
        setTimeout(() => p.remove(), 3000);
      }
    }

    btn.addEventListener('click', () => {
      if (opened) {
        message.classList.toggle('show');
        return;
      }
      opened = true;
      gift.classList.add('open');
      message.classList.add('show');
      btn.textContent = 'Yana bir bor o‘qish ♡';
      hint.textContent = 'Senga faqat yaxshiliklar tilayman!';
      burst();
    });
  </script>
</body>
</html>
