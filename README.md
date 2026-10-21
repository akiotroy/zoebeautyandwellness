<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8"><meta name="viewport" content="width=device-width,initial-scale=1">
<title>Zoë Beauty & Wellness</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600&family=Inter:wght@300;400;500&family=Caveat:wght@400;500&display=swap" rel="stylesheet">
<style>
/* ===== EDIT YOUR DETAILS HERE (also see the CONFIG in the script at the bottom) ===== */
:root{--sage:#9AAA9C;--blue:#89AABD;--cream:#F3F0E8;--sand:#CFC2AF;--char:#3F4748;--ink:#34546B;--mist:#DDE5EA}
*{box-sizing:border-box;margin:0}
html{scroll-behavior:smooth}
body{background:var(--cream);color:var(--char);font:300 16px/1.7 Inter,sans-serif;overflow-x:hidden}
h1,h2,h3,.serif{font-family:'Cormorant Garamond',serif;font-weight:500;color:var(--ink);line-height:1.1}
.script{font-family:Caveat,cursive;color:var(--ink);font-size:1.9rem}
a{color:inherit;text-decoration:none}
:focus-visible{outline:2px solid var(--ink);outline-offset:3px}
.label{font-size:11px;text-transform:uppercase;letter-spacing:.28em;opacity:.75}
.wrap{max-width:1100px;margin:0 auto;padding:70px 24px}
.center{text-align:center}
.rule{height:1px;width:64px;background:var(--sand);margin:22px auto 0}
.hd{max-width:640px;margin:0 auto 48px;text-align:center}
.hd h2{font-size:clamp(2.2rem,5vw,3.2rem);margin:10px 0}
.btn{display:inline-flex;align-items:center;justify-content:center;min-height:46px;padding:0 28px;font-size:11px;text-transform:uppercase;letter-spacing:.25em;border:1px solid var(--ink);background:var(--ink);color:var(--cream);cursor:pointer;border-radius:2px;transition:all .3s ease;font-family:inherit;box-shadow:0 4px 12px rgba(52,84,107,0.15)}
.btn:hover{transform:translateY(-2px);background:var(--char);border-color:var(--char);box-shadow:0 6px 18px rgba(63,71,72,0.2)}
.btn.out{background:transparent;color:var(--ink);box-shadow:none}.btn.out:hover{background:var(--ink);color:var(--cream)}
/* nav */
header{position:sticky;top:0;z-index:50;background:rgba(243,240,232,.92);backdrop-filter:blur(10px);-webkit-backdrop-filter:blur(10px);border-bottom:1px solid rgba(207,194,175,.5);transition:all .3s}
.bar{max-width:1100px;margin:auto;padding:0 24px;height:78px;display:flex;align-items:center;justify-content:space-between;gap:20px}
.logo{line-height:1}.logo b{font:500 2rem 'Cormorant Garamond',serif;letter-spacing:.08em;color:var(--ink)}.logo small{display:block;font-size:8px;letter-spacing:.35em;margin-top:4px}
nav.d{display:flex;gap:22px}
nav a{font-size:11px;text-transform:uppercase;letter-spacing:.2em;padding-bottom:4px;border-bottom:1px solid transparent;transition:all .2s}
nav a:hover{border-color:var(--sand)}nav a.on{border-color:var(--ink);color:var(--ink);font-weight:500}
#burger{display:none;background:none;border:0;padding:10px;cursor:pointer}
#burger i{display:block;width:24px;height:1px;background:var(--ink);margin:6px 0;transition:all .3s}
#mob{display:none;flex-direction:column;gap:16px;padding:20px 24px;border-top:1px solid var(--sand);background:var(--cream)}
#mob.open{display:flex}#mob a{font:500 1.7rem 'Cormorant Garamond',serif;color:var(--char);letter-spacing:0;text-transform:none;border:0}#mob a.on{color:var(--ink)}
@media(max-width:960px){nav.d,.bookbtn{display:none}#burger{display:block}}
/* pages */
.page{display:none}.page.show{display:block;animation:fadeIn .5s ease-out}
@keyframes fadeIn { from { opacity: 0; transform: translateY(6px); } to { opacity: 1; transform: translateY(0); } }
.rev{opacity:0;transform:translateY(20px);transition:opacity 0.9s cubic-bezier(0.16, 1, 0.3, 1),transform 0.9s cubic-bezier(0.16, 1, 0.3, 1)}.rev.in{opacity:1;transform:none}
@media(prefers-reduced-motion:reduce){.rev{opacity:1;transform:none;transition:none}}
/* hero */
.hero{display:grid;grid-template-columns:1fr 1fr;min-height:85vh}
.hero .t{display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;padding:60px 32px}
.hero h1{font-size:clamp(5rem,12vw,8.5rem);letter-spacing:.06em}
.hero p.l{max-width:440px;margin-top:22px}
.hero .ph{position:relative;min-height:450px;overflow:hidden}
.hero .ph .script{position:absolute;right:28px;bottom:26px;color:#fff;text-shadow:0 2px 10px rgba(0,0,0,.6);z-index:2;font-size:2.2rem}
.hero .ph::after{content:'';position:absolute;inset:0;background:linear-gradient(to top, rgba(52,84,107,0.4) 0%, transparent 50%);z-index:1}
.btns{display:flex;gap:12px;margin-top:30px;flex-wrap:wrap;justify-content:center}
@media(max-width:800px){.hero{grid-template-columns:1fr}.hero .ph{min-height:360px}}
/* images */
.im{background:linear-gradient(135deg,var(--mist),var(--sand));overflow:hidden;position:relative;border-radius:2px}
.im img{width:100%;height:100%;object-fit:cover;display:block;transition:transform 0.9s cubic-bezier(0.16, 1, 0.3, 1), filter 0.5s ease}
.im:hover img{transform:scale(1.05);filter:brightness(1.03)}
.hero .im{position:absolute;inset:0}
/* grids & cards */
.g{display:grid;gap:22px}.g3{grid-template-columns:repeat(auto-fit,minmax(260px,1fr))}.g4{grid-template-columns:repeat(auto-fit,minmax(200px,1fr))}
.card{background:rgba(221,229,234,.5);border:1px solid rgba(207,194,175,.6);padding:28px 24px;text-align:center;transition:all .3s ease;border-radius:3px;backdrop-filter:blur(4px)}
.card:hover{transform:translateY(-6px);box-shadow:0 14px 32px rgba(52,84,107,.12);border-color:var(--blue)}
.card .av{width:110px;height:110px;border-radius:50%;margin:0 auto 20px;box-shadow:0 6px 16px rgba(0,0,0,0.08);border:2px solid var(--cream)}
.card h3{font:400 12px Inter;letter-spacing:.3em;text-transform:uppercase;color:var(--ink)}
.card p.pr,.price{font:500 1.5rem 'Cormorant Garamond',serif;color:var(--ink)}
.more{display:inline-block;margin-top:14px;font-size:11px;letter-spacing:.25em;text-transform:uppercase;border-bottom:1px solid var(--ink);padding-bottom:3px;transition:color .2s, border-color .2s}
.more:hover{color:var(--sage);border-color:var(--sage)}
.band{background:rgba(137,170,189,.2);position:relative;overflow:hidden}
.why{background:var(--cream);border:1px solid var(--sand);padding:26px 14px;font:500 1.3rem 'Cormorant Garamond',serif;color:var(--ink);text-align:center;box-shadow:0 4px 12px rgba(0,0,0,0.02);transition:transform .3s}
.why:hover{transform:translateY(-3px)}
.gal{display:grid;grid-template-columns:repeat(3,1fr);gap:14px}.gal .im{aspect-ratio:1;cursor:pointer;box-shadow:0 4px 12px rgba(0,0,0,0.05)}
@media(max-width:600px){.gal{grid-template-columns:repeat(2,1fr)}}
/* service rows */
.row{display:grid;grid-template-columns:1fr 1fr;gap:48px;align-items:center;margin-bottom:80px;scroll-margin-top:100px}
.row .im{aspect-ratio:4/3;box-shadow:0 10px 25px rgba(0,0,0,0.06)}.row:nth-child(even) .im{order:2}
@media(max-width:800px){.row{grid-template-columns:1fr;gap:24px}.row:nth-child(even) .im{order:0}}
ul.lst{list-style:none;padding:0;margin:18px 0;border-top:1px solid var(--sand)}ul.lst li{padding:10px 0;border-bottom:1px solid var(--sand);font-size:14px}
/* forms */
form.f{background:rgba(221,229,234,.6);border:1px solid var(--sand);padding:clamp(22px,5vw,44px);display:grid;gap:18px;max-width:640px;margin:auto;box-shadow:0 8px 24px rgba(0,0,0,0.03)}
form label{display:block}form label span{display:block;margin-bottom:6px}
input,select,textarea{width:100%;padding:13px 14px;border:1px solid var(--sand);background:rgba(243,240,232,.9);font:inherit;font-size:14px;border-radius:2px;color:var(--char);transition:border-color .2s}
input:focus,select:focus,textarea:focus{border-color:var(--ink);outline:none;background:#fff}
.r2{display:grid;grid-template-columns:1fr 1fr;gap:16px}@media(max-width:560px){.r2{grid-template-columns:1fr}}
.ok{background:var(--mist);padding:36px;text-align:center;font:500 1.6rem 'Cormorant Garamond',serif;color:var(--ink);max-width:640px;margin:auto;border:1px solid var(--sand)}
.amt{display:grid;grid-template-columns:repeat(auto-fit,minmax(110px,1fr));gap:14px;max-width:640px;margin:0 auto 26px}
.amt button{padding:20px 10px;border:1px solid var(--sand);background:rgba(221,229,234,.6);font:500 1.7rem 'Cormorant Garamond',serif;color:var(--ink);cursor:pointer;transition:.3s}
.amt button:hover{transform:translateY(-2px);background:rgba(137,170,189,.2)}.amt button.sel{background:rgba(137,170,189,.5);border-color:var(--ink)}
.cats{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:26px}
.cats button{padding:12px 18px;border:1px solid var(--sand);background:none;font:400 11px Inter;letter-spacing:.22em;text-transform:uppercase;cursor:pointer;color:var(--char);transition:all .2s}
.cats button.sel{background:var(--ink);color:var(--cream);border-color:var(--ink)}
.prod .ph{aspect-ratio:1;margin-bottom:16px;overflow:hidden;border-radius:2px}
dl div{display:flex;justify-content:space-between;gap:16px;padding:12px 0;border-bottom:1px solid var(--sand);font-size:14px}dl{border-top:1px solid var(--sand);margin-bottom:26px}
.map{aspect-ratio:4/3;background:rgba(207,194,175,.3);border:1px solid var(--sand);display:flex;align-items:center;justify-content:center;text-align:center;padding:16px;color:var(--ink)}
footer{background:var(--mist);border-top:1px solid var(--sand)}
footer .in{max-width:1100px;margin:auto;padding:54px 24px;display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:36px}
footer ul{list-style:none;padding:0;display:grid;grid-template-columns:1fr 1fr;gap:8px;font-size:14px}
footer .cp{border-top:1px solid rgba(207,194,175,.7);text-align:center;font-size:12px;padding:18px}
.leaf{width:34px;display:block;margin:0 auto 12px}

/* Lightbox Modal */
#lightbox{display:none;position:fixed;inset:0;background:rgba(52,84,107,0.85);backdrop-filter:blur(8px);z-index:100;align-items:center;justify-content:center;padding:24px;cursor:pointer}
#lightbox.active{display:flex;animation:fadeIn .3s ease}
#lightbox img{max-width:90vw;max-height:85vh;object-fit:contain;border-radius:2px;box-shadow:0 12px 40px rgba(0,0,0,0.3)}
</style>
</head>
<body>
<header>
  <div class="bar">
    <a href="#/" class="logo" aria-label="Zoë home"><b>ZOË</b><small>BEAUTY &amp; WELLNESS</small></a>
    <nav class="d" id="nav" aria-label="Main"></nav>
    <a href="#/book" class="btn bookbtn" style="min-height:40px">Book</a>
    <button id="burger" aria-label="Menu" aria-expanded="false"><i></i><i></i><i style="width:16px;margin-left:8px"></i></button>
  </div>
  <nav id="mob" aria-label="Mobile"></nav>
</header>

<main id="main">

<!-- HOME -->
<section class="page" id="home">
  <div class="hero">
    <div class="t">
      <svg class="leaf" style="width:56px" viewBox="0 0 60 90" fill="none" stroke="#34546B" stroke-width="1" stroke-linecap="round"><path d="M30 88V30M30 60c-10-2-16-10-16-20 10 2 16 10 16 20zM30 48c10-2 16-10 16-20-10 2-16 10-16 20zM30 30C22 22 22 10 30 2c8 8 8 20 0 28z"/></svg>
      <h1>ZOË</h1><p class="label" style="letter-spacing:.4em;margin:14px 0 18px">BEAUTY &amp; WELLNESS</p>
      <p class="script" id="tag"></p>
      <p class="l">Zoë Beauty &amp; Wellness is a calm, intimate space where beauty, self-care and wellness come together. We believe in feeling good in your skin — inside and out. It's more than a treatment, it's a moment for you.</p>
      <div class="btns"><a class="btn" href="#/book">Book an appointment</a><a class="btn out" href="#/services">Explore services</a></div>
    </div>
    <div class="ph"><div class="im"><img src="https://images.unsplash.com/photo-1540555700478-4be289fbecef?auto=format&fit=crop&w=1200&q=80" alt="Calm treatment room with dusty blue accent, plants and treatment bed"></div><span class="script">small space, big dreams ♡</span></div>
  </div>
  <div class="wrap">
    <div class="hd rev"><p class="label">Welcome</p><h2>Small space, big care.</h2><p>A private studio where you can slow down, feel comfortable and take time for yourself.</p><div class="rule"></div></div>
    <div class="hd rev"><p class="label">What we offer</p><h2>Treatments, thoughtfully chosen</h2><div class="rule"></div></div>
    <div class="g g3" id="homeServices"></div>
  </div>
  <div class="band"><div class="wrap"><div class="hd rev"><p class="label">Why Zoë?</p><h2>Care that feels personal</h2><div class="rule"></div></div><div class="g g4" id="why"></div></div></div>
  <div class="wrap"><div class="hd rev"><p class="label">Gallery</p><h2>Inside the studio</h2><div class="rule"></div></div><div class="gal rev" data-gal></div></div>
  <div class="band center wrap rev"><h2 style="font-size:clamp(2.2rem,5vw,3.2rem);margin-bottom:26px">Your time. Your space. Your moment.</h2><a class="btn" href="#/book">Book your appointment</a></div>
</section>

<!-- SERVICES -->
<section class="page" id="services">
  <div class="wrap">
    <div class="hd rev"><p class="label">Services</p><h2>Services</h2><p>Beauty treatments and moments of self-care, thoughtfully designed around you.</p><div class="rule"></div></div>
    <div id="svcList"></div>
  </div>
  <div class="band center wrap"><h2 style="font-size:2.4rem;margin-bottom:10px">Not sure what to book?</h2><p style="margin-bottom:24px">Not sure which treatment is right for you? We're happy to help you choose.</p><a class="btn" href="#/contact">Get in touch</a></div>
</section>

<!-- ABOUT -->
<section class="page" id="about">
  <div class="wrap">
    <div class="hd rev"><p class="label">About</p><h2>More than a treatment.</h2><p>At Zoë Beauty &amp; Wellness, we believe self-care should feel natural, calming and personal.</p><div class="rule"></div></div>
    <div class="row rev"><div class="im" style="aspect-ratio:4/5"><img src="https://images.unsplash.com/photo-1526047932273-341f2a7631f9?auto=format&fit=crop&w=800&q=80" alt="Blue hydrangeas beside a candle" loading="lazy"></div>
      <div><p class="label">Our philosophy</p><p class="serif" style="font-size:2rem;margin-top:10px">The studio is an intimate space where you can slow down, feel comfortable and take time for yourself.</p></div></div>
    <div class="g g4 rev" id="values" style="margin-bottom:80px"></div>
    <div class="row rev"><div><p class="label">The space</p><h2 style="font-size:2.6rem;margin:10px 0">Small, warm and personal</h2>
      <ul class="lst"><li>Approximately 3m × 3.5m</li><li>Natural light</li><li>Treatment bed</li><li>Beauty / manicure station</li><li>Waiting area</li><li>Storage</li><li>Plants and calming decor</li></ul></div>
      <div class="im"><img src="https://images.unsplash.com/photo-1586023492125-27b2c045efd7?auto=format&fit=crop&w=800&q=80" alt="Armchair with a blue cushion beside a plant" loading="lazy"></div></div>
  </div>
  <div class="band center wrap"><h2 style="font-size:2.4rem;margin-bottom:24px">Your time. Your space. Your moment.</h2><a class="btn" href="#/book">Book your appointment</a></div>
</section>

<!-- BOOK -->
<section class="page" id="book">
  <div class="wrap">
    <div class="hd rev"><p class="label">Book</p><h2>Make time for you.</h2><div class="rule"></div></div>
    <form class="f" data-kind="booking" data-done="Thank you. We'll be in touch to confirm your appointment.">
      <label><span class="label">Name</span><input name="name" required></label>
      <label><span class="label">Email</span><input name="email" type="email" required></label>
      <label><span class="label">Phone</span><input name="phone" type="tel"></label>
      <label><span class="label">Select service</span><select name="service" required><option value="">Choose…</option><option>Nails</option><option>Brows &amp; Lashes</option><option>Facials</option><option>Massage</option><option>Other</option></select></label>
      <div class="r2"><label><span class="label">Preferred date</span><input name="date" type="date"></label><label><span class="label">Preferred time</span><input name="time" type="time"></label></div>
      <label><span class="label">Additional notes</span><textarea name="notes" rows="4"></textarea></label>
      <p style="font-size:12px">Appointments are confirmed once we have received your booking request.</p>
      <button class="btn" type="submit">Request appointment</button>
    </form>
    <div class="center" style="margin-top:50px"><p class="script">Prefer to chat?</p><br><a class="btn out" id="wa" target="_blank" rel="noreferrer">Book via WhatsApp</a></div>
  </div>
</section>

<!-- SHOP -->
<section class="page" id="shop">
  <div class="wrap">
    <div class="hd rev"><p class="label">Shop</p><h2>Self-care to take home.</h2><p>Handpicked skincare, body care, and nail products aligned with our calm philosophy.</p><div class="rule"></div></div>
    <div style="display:flex;justify-content:space-between;flex-wrap:wrap;gap:12px;align-items:flex-start"><div class="cats" id="cats" role="tablist"></div><p class="label" aria-live="polite">Basket (<span id="bk">0</span>)</p></div>
    <div class="g g4" id="prods"></div>
  </div>
</section>

<!-- GIFT VOUCHERS -->
<section class="page" id="gift-vouchers">
  <div class="wrap">
    <div class="hd rev"><p class="label">Gift vouchers</p><h2>A little self-care goes a long way.</h2><div class="rule"></div></div>
    <div class="amt" id="amts" role="radiogroup" aria-label="Voucher amount"></div>
    <form class="f" data-kind="voucher" data-done="Thank you. Voucher request received (payment coming soon).">
      <input type="hidden" name="amount" id="amtField" value="500">
      <label><span class="label">Recipient name</span><input name="recipient" required></label>
      <label><span class="label">Sender name</span><input name="sender" required></label>
      <label><span class="label">Your email</span><input name="email" type="email" required></label>
      <label><span class="label">Personal message</span><textarea name="message" rows="4"></textarea></label>
      <p style="font-size:12px">Selected amount: <b id="amtShow">R500</b></p>
      <button class="btn" type="submit">Purchase gift voucher</button>
    </form>
  </div>
</section>

<!-- CONTACT -->
<section class="page" id="contact">
  <div class="wrap">
    <div class="hd rev"><p class="label">Contact</p><h2>Come and slow down.</h2><p>Zoë Beauty &amp; Wellness · Centurion, South Africa. Bookings recommended.</p><div class="rule"></div></div>
    <div class="g g3" style="grid-template-columns:repeat(auto-fit,minmax(300px,1fr));gap:40px">
      <div><dl id="info"></dl><div class="map label">Map placeholder — embed Google Maps here</div></div>
      <form class="f" data-kind="contact" data-done="Thank you. We'll reply soon." style="margin:0;max-width:none">
        <label><span class="label">Name</span><input name="name" required></label>
        <label><span class="label">Email</span><input name="email" type="email" required></label>
        <label><span class="label">Message</span><textarea name="message" rows="5" required></textarea></label>
        <button class="btn" type="submit">Send message</button>
      </form>
    </div>
    <div class="hd" style="margin-top:80px"><p class="label">Instagram</p><h2 id="igh"></h2><div class="rule"></div></div>
    <div class="gal" data-gal></div>
  </div>
</section>

</main>

<!-- Lightbox Modal -->
<div id="lightbox" aria-hidden="true">
  <img src="" alt="Enlarged gallery view">
</div>

<footer>
  <div class="in">
    <div><svg class="leaf" style="margin:0 0 12px" viewBox="0 0 60 90" fill="none" stroke="#34546B" stroke-width="1" stroke-linecap="round"><path d="M30 88V30M30 60c-10-2-16-10-16-20 10 2 16 10 16 20zM30 48c10-2 16-10 16-20-10 2-16 10-16 20zM30 30C22 22 22 10 30 2c8 8 8 20 0 28z"/></svg>
      <p class="serif" style="font-size:2.4rem;letter-spacing:.08em">ZOË</p><p class="label">BEAUTY &amp; WELLNESS</p><p class="script" id="ftag" style="margin-top:12px"></p></div>
    <ul id="fnav"></ul>
    <div style="font-size:14px;display:grid;gap:8px;align-content:start"><a id="ig" target="_blank" rel="noreferrer"></a><a id="wa2" target="_blank" rel="noreferrer">WhatsApp</a><p id="area"></p></div>
  </div>
  <p class="cp">© Zoë Beauty &amp; Wellness. All rights reserved.</p>
</footer>

<script>
/* ============ CONFIG: change details, prices and products here ============ */
const SITE={
  tagline:'look good · feel good · be well',
  phone:'[Phone number]', whatsappNumber:'[WhatsApp number]', email:'[Email address]', address:'[Full address]',
  area:'Centurion, South Africa',
  instagram:'https://instagram.com/zoe.beautywellness', handle:'@zoe.beautywellness',
  whatsapp:'https://wa.me/27000000000?text=Hi%20Zo%C3%AB%2C%20I%27d%20like%20to%20book' // TODO: replace with real number
};

/* Moodboard Imagery Mapping */
const IMAGES = {
  room: 'https://images.unsplash.com/photo-1540555700478-4be289fbecef?auto=format&fit=crop&w=1200&q=80',
  flowers: 'https://images.unsplash.com/photo-1526047932273-341f2a7631f9?auto=format&fit=crop&w=800&q=80',
  shelf: 'https://images.unsplash.com/photo-1616486338812-3dadae4b4ace?auto=format&fit=crop&w=800&q=80',
  nails: 'https://images.unsplash.com/photo-1604654894610-df63bc536371?auto=format&fit=crop&w=800&q=80',
  chair: 'https://images.unsplash.com/photo-1586023492125-27b2c045efd7?auto=format&fit=crop&w=800&q=80',
  tea: 'https://images.unsplash.com/photo-1576092768241-dec231879fc3?auto=format&fit=crop&w=800&q=80',
  's-nails': 'https://images.unsplash.com/photo-1632345031435-8727f6897d53?auto=format&fit=crop&w=400&q=80',
  's-brows': 'https://images.unsplash.com/photo-1522337360788-8b13dee7a37e?auto=format&fit=crop&w=400&q=80',
  's-facials': 'https://images.unsplash.com/photo-1512290900673-7002ddb928f0?auto=format&fit=crop&w=400&q=80',
  's-massage': 'https://images.unsplash.com/photo-1544161515-4ab6ce6db874?auto=format&fit=crop&w=400&q=80',
  's-retail': 'https://images.unsplash.com/photo-1608248597261-833258657640?auto=format&fit=crop&w=400&q=80',
  prod1: 'https://images.unsplash.com/photo-1556228720-195a672e8a03?auto=format&fit=crop&w=600&q=80',
  prod2: 'https://images.unsplash.com/photo-1608248597261-833258657640?auto=format&fit=crop&w=600&q=80',
  prod3: 'https://images.unsplash.com/photo-1620916566398-39f1143ab7be?auto=format&fit=crop&w=600&q=80'
};

const SERVICES=[
 {id:'nails',name:'Nails',blurb:'Manicures · Gel / BIAB · Nail art',items:['Manicures','Gel','BIAB','Nail art'],range:'R150 – R350',img:'nails',av:'s-nails',long:'Neat, nourished hands and nails, finished in soft, natural tones.'},
 {id:'brows-lashes',name:'Brows & Lashes',blurb:'Brow shaping · Tinting · Lash lifts',items:['Brow shaping','Tinting','Lash lifts'],range:'R120 – R450',img:'flowers',av:'s-brows',long:'Subtle definition that frames your face and suits you.'},
 {id:'facials',name:'Facials',blurb:'Express glow · Deep cleanse · Hydrating',items:['Express glow','Deep cleanse','Hydrating'],range:'R250 – R600',img:'shelf',av:'s-facials',long:'A quiet hour of skin care, tailored to what your skin needs today.'},
 {id:'massage',name:'Massage',blurb:'Relaxation · Back, neck & shoulders · Full body',items:['Relaxation','Back, neck & shoulders','Full body'],range:'R250 – R550',img:'room',av:'s-massage',long:'Unhurried touch to release tension and help you reset.'},
 {id:'retail',name:'Retail Products',blurb:'Skincare · Body care · Nail care',items:['Skincare','Body care','Nail care'],range:'R50 – R800',img:'chair',av:'s-retail',long:'Self-care to take home, chosen with care.'}
];

const WHY=['Personalised care','Calm environment','Small intimate studio','Quality products','Hygiene','Self-care','Beauty and wellness together'];
const VALUES=[['Calm','A quiet room, soft light and no rush.'],['Renew','Leave feeling refreshed, inside and out.'],['Balance','Beauty and wellness, side by side.'],['Self care','Not a luxury, a necessity.']];
const CATS=['Skincare','Body care','Nail care','Gift ideas'];
const PRODUCTS=CATS.flatMap((c,i)=>[1,2].map(n=>({cat:c,name:'Nourishing '+c+' '+n,desc:'Handcrafted gentle formulation for daily care.',price:[120,250,80,450][i]+n*30,img:[IMAGES.prod1,IMAGES.prod2,IMAGES.prod3][(i+n)%3]})));
const GALLERY=['flowers','shelf','nails','chair','tea','room'];
const NAV=[['Home','/'],['Services','/services'],['About','/about'],['Book','/book'],['Shop','/shop'],['Gift Vouchers','/gift-vouchers'],['Contact','/contact']];

async function submitForm(kind,data){console.info('[Zoë]',kind,data);return {ok:true}}

/* ============ Build content ============ */
const $=s=>document.querySelector(s),$$=s=>[...document.querySelectorAll(s)];
const img=(n,alt,cls='')=>`<img src="${IMAGES[n]||n}" alt="${alt}" loading="lazy" class="${cls}">`;

$('#tag').textContent=$('#ftag').textContent=SITE.tagline;
$('#nav').innerHTML=NAV.filter(n=>n[1]!=='/book').map(([t,h])=>`<a href="#${h}" data-r="${h}">${t}</a>`).join('');
$('#mob').innerHTML=NAV.map(([t,h])=>`<a href="#${h}" data-r="${h}">${t}</a>`).join('');
$('#fnav').innerHTML=NAV.map(([t,h])=>`<li><a href="#${h}">${t}</a></li>`).join('');
$('#ig').textContent='Instagram '+SITE.handle;$('#ig').href=SITE.instagram;$('#wa2').href=$('#wa').href=SITE.whatsapp;$('#area').textContent=SITE.area;$('#igh').textContent=SITE.handle;

$('#homeServices').innerHTML=SERVICES.map(s=>`<article class="card rev"><div class="av im">${img(s.av,s.name)}</div><h3>${s.name}</h3><p style="margin:10px 0;font-size:14px">${s.blurb}</p><p class="pr">${s.range}</p><a class="more" href="#/services/${s.id}">Learn more</a></article>`).join('');
$('#why').innerHTML=WHY.map(w=>`<div class="why rev">${w}</div>`).join('');

/* Interactive Gallery */
$$('[data-gal]').forEach(g=>g.innerHTML=GALLERY.map(n=>`<div class="im" onclick="openLightbox('${IMAGES[n]}')">${img(n,'Zoë studio mood')}</div>`).join(''));

function openLightbox(src){
  const lb = $('#lightbox');
  lb.querySelector('img').src = src;
  lb.classList.add('active');
  lb.setAttribute('aria-hidden','false');
}
$('#lightbox').onclick=function(){
  this.classList.remove('active');
  this.setAttribute('aria-hidden','true');
};

$('#svcList').innerHTML=SERVICES.map(s=>`<div class="row rev" id="${s.id}"><div class="im">${img(s.img,s.name)}</div><div><h2 style="font-size:2.8rem">${s.name}</h2><p style="margin-top:10px">${s.long}</p><ul class="lst">${s.items.map(i=>`<li>${i}</li>`).join('')}</ul><p class="label">Price range</p><p class="price" style="font-size:2.2rem">${s.range}</p><br>${s.id==='retail'?'<a class="btn out" href="#/shop">Visit the shop</a>':'<a class="btn" href="#/book">Book '+s.name+'</a>'}</div></div>`).join('');
$('#values').innerHTML=VALUES.map(([t,d])=>`<div class="card"><h3>${t}</h3><p style="font-size:14px;margin-top:10px">${d}</p></div>`).join('');
$('#info').innerHTML=[['Phone',SITE.phone],['WhatsApp',SITE.whatsappNumber],['Email',SITE.email],['Instagram',SITE.handle],['Address',SITE.address]].map(([k,v])=>`<div><dt class="label">${k}</dt><dd>${v}</dd></div>`).join('');

/* shop */
let cat=CATS[0],basket=0;
function drawShop(){
 $('#cats').innerHTML=CATS.map(c=>`<button role="tab" aria-selected="${c===cat}" class="${c===cat?'sel':''}" data-c="${c}">${c}</button>`).join('');
 $('#prods').innerHTML=PRODUCTS.filter(p=>p.cat===cat).map(p=>`<article class="card prod"><div class="im ph"><img src="${p.img}" alt="${p.name}" loading="lazy"></div><h3 style="font:500 1.3rem 'Cormorant Garamond',serif;letter-spacing:0;text-transform:none;color:var(--ink)">${p.name}</h3><p style="font-size:14px;margin:8px 0">${p.desc}</p><p class="price" style="margin-bottom:14px">R${p.price}</p><button class="btn out add" style="width:100%">Add to basket</button></article>`).join('');
}
drawShop();
$('#cats').onclick=e=>{if(e.target.dataset.c){cat=e.target.dataset.c;drawShop()}};
$('#prods').onclick=e=>{if(e.target.classList.contains('add')){$('#bk').textContent=++basket}};

/* vouchers */
let amt=500;
function drawAmts(){$('#amts').innerHTML=[250,500,750,1000].map(a=>`<button role="radio" aria-checked="${a===amt}" class="${a===amt?'sel':''}" data-a="${a}">R${a.toLocaleString('en-ZA')}</button>`).join('');$('#amtField').value=amt;$('#amtShow').textContent='R'+amt}
drawAmts();$('#amts').onclick=e=>{if(e.target.dataset.a){amt=+e.target.dataset.a;drawAmts()}};  /* forms */ $$('form.f').forEach(f=>f.addEventListener('submit',async e=>{
 e.preventDefault();await submitForm(f.dataset.kind,Object.fromEntries(new FormData(f)));
 f.outerHTML=`<div class="ok" role="status">${f.dataset.done}</div>`;
}));

/* mobile menu */
$('#burger').onclick=()=>{const o=$('#mob').classList.toggle('open');$('#burger').setAttribute('aria-expanded',o)};

/* router (hash based: #/services, #/about, ...) */
const io=new IntersectionObserver(es=>es.forEach(e=>{if(e.isIntersecting){e.target.classList.add('in');io.unobserve(e.target)}}),{threshold:.12});
function route(){
 const [,p='',sub]=location.hash.split('/'); const id=p||'home';
 const pg=document.getElementById(id)&&document.getElementById(id).classList.contains('page')?id:'home';
 $$('.page').forEach(s=>s.classList.toggle('show',s.id===pg));$$
('[data-r]').forEach(a=>a.dataset&&a.classList.toggle('on',a.dataset.r==='/'+(pg==='home'?'':pg)));
 $('#mob').classList.remove('open'); document.title=(pg==='home'?'':pg.replace('-',' ').replace(/^./,c=>c.toUpperCase())+' · ')+'Zoë Beauty & Wellness'; $$('.page.show .rev').forEach(el=>io.observe(el));
 if(sub&&document.getElementById(sub))setTimeout(()=>document.getElementById(sub).scrollIntoView({behavior:'smooth'}),60);else window.scrollTo(0,0);
}
addEventListener('hashchange',route);route();
</script>
</body>
</html>
