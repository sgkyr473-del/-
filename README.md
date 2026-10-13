# -

<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ریاضی فول فول هفتم تا دوازدهم | استاد جوکار</title>
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  :root{
    --bg1:#0b1026; --bg2:#1a0b2e;
    --card: rgba(255,255,255,0.06);
    --stroke: rgba(255,255,255,0.12);
    --accent:#7c5cff; --accent2:#00e0c6;
    --gold:#ffc93c; --text:#eaeaff; --muted:#a5a8c8;
  }
  body{
    font-family: Vazirmatn, "Segoe UI", Tahoma, sans-serif;
    background:
      radial-gradient(1000px 600px at 90% -10%, #2b1a5e 0%, transparent 60%),
      radial-gradient(900px 600px at -10% 20%, #063b4a 0%, transparent 55%),
      linear-gradient(160deg, var(--bg1), var(--bg2));
    color: var(--text); min-height: 100vh; padding: 18px; line-height: 1.9;
  }

  header{
    max-width: 1150px; margin: 0 auto 22px;
    background: linear-gradient(135deg, rgba(124,92,255,.22), rgba(0,224,198,.12));
    border: 1px solid var(--stroke); border-radius: 24px;
    padding: 26px 22px; text-align: center;
    backdrop-filter: blur(14px); position: relative; overflow: hidden;
  }
  header::after{
    content:"∑ ∫ π √ ∞ Δ θ ≠ ≤ ≥ ∈ ∀";
    position:absolute; inset:0; font-size: 80px; opacity:.05;
    letter-spacing: 28px; display:flex; align-items:center; justify-content:center;
    pointer-events:none;
  }
  h1{
    font-size: clamp(24px, 5vw, 42px);
    background: linear-gradient(90deg, var(--gold), var(--accent2), var(--accent));
    -webkit-background-clip: text; background-clip:text; color: transparent;
    font-weight: 800; letter-spacing: -1px;
  }
  .subtitle{ color: var(--muted); font-size: 15px; margin-top: 6px; }
  .badges{ display:flex; gap:10px; justify-content:center; flex-wrap:wrap; margin-top:14px; }
  .badge{
    background: rgba(255,255,255,.07); border:1px solid var(--stroke);
    padding: 6px 14px; border-radius: 999px; font-size: 13px;
  }
  .badge.gold{ border-color: rgba(255,201,60,.5); color: var(--gold); }
  .badge.teal{ border-color: rgba(0,224,198,.5); color: var(--accent2); }

  .wrap{
    max-width: 1150px; margin: 0 auto;
    display: grid; grid-template-columns: 1fr 1fr; gap: 18px;
  }
  @media (max-width: 950px){ .wrap{ grid-template-columns: 1fr; } }

  .card{
    background: var(--card); border: 1px solid var(--stroke);
    border-radius: 20px; padding: 18px; backdrop-filter: blur(12px);
  }
  .card h2{ font-size: 18px; margin-bottom: 12px; display:flex; align-items:center; gap:8px; }
  .card h2 span{ font-size: 20px; }

  /* Tools */
  .tool{ margin-bottom: 16px; }
  .tool:last-child{ margin-bottom: 0; }
  .tool label{ font-size: 13px; color: var(--muted); display:block; margin-bottom:6px; }

  input[type="text"], input[type="number"]{
    width: 100%; background: rgba(0,0,0,.3);
    border: 1px solid var(--stroke); border-radius: 12px;
    padding: 11px 13px; color: var(--text);
    font-family: inherit; font-size: 15px; outline: none; transition: .2s;
  }
  input:focus{ border-color: var(--accent); box-shadow: 0 0 0 3px rgba(124,92,255,.18); }
  .row{ display:flex; gap:8px; }
  .row > *{ flex:1; }

  button{
    font-family: inherit; cursor: pointer; border: none;
    border-radius: 12px; padding: 11px 16px;
    font-size: 14px; font-weight: 600; color: #fff;
    background: linear-gradient(135deg, var(--accent), #4a2fd6);
    transition: .2s;
  }
  button:hover{ transform: translateY(-2px); box-shadow: 0 8px 22px rgba(124,92,255,.35); }
  button:active{ transform: translateY(0); }

  .result{
    margin-top: 10px; background: rgba(0,224,198,.08);
    border: 1px dashed rgba(0,224,198,.35); border-radius: 12px;
    padding: 11px 13px; font-size: 14px; min-height: 44px;
    white-space: pre-line; color: #d6fff9;
  }
  .result:empty{ display:none; }

  /* Grade Browser */
  .grade-tabs{
    display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 12px;
  }
  .gtab{
    flex:1; min-width: 60px;
    background: rgba(255,255,255,.06); border: 1px solid var(--stroke);
    color: var(--muted); font-family: inherit; font-size: 13px;
    padding: 8px 4px; border-radius: 10px; cursor: pointer; transition: .2s;
    font-weight: 600;
  }
  .gtab:hover{ color:#fff; background: rgba(124,92,255,.2); }
  .gtab.active{
    background: linear-gradient(135deg, var(--accent), #4a2fd6);
    color: #fff; border-color: var(--accent);
    box-shadow: 0 6px 18px rgba(124,92,255,.35);
  }

  .grade-content{ animation: fadeIn .25s ease; }
  @keyframes fadeIn{ from{ opacity:0; transform: translateY(6px);} to{ opacity:1; } }

  .grade-title{
    font-size: 15px; font-weight: 700; color: var(--gold);
    margin-bottom: 10px; padding-bottom: 6px;
    border-bottom: 1px dashed var(--stroke);
  }
  .chapter{
    background: rgba(255,255,255,.04); border: 1px solid var(--stroke);
    border-radius: 12px; padding: 10px 12px; margin-bottom: 8px;
    font-size: 13.5px; transition: .2s;
  }
  .chapter:hover{ background: rgba(0,224,198,.08); border-color: rgba(0,224,198,.3); }
  .chapter b{ color: var(--accent2); display: block; margin-bottom: 4px; font-size: 14px; }
  .chapter ul{ list-style: none; padding-right: 6px; }
  .chapter li{ color: var(--muted); position: relative; padding-right: 14px; font-size: 12.5px; }
  .chapter li::before{ content:"•"; color: var(--gold); position:absolute; right:0; }

  /* Formula grid */
  .formula-grid{ display:grid; grid-template-columns: 1fr 1fr; gap:10px; }
  @media (max-width:520px){ .formula-grid{ grid-template-columns: 1fr; } }
  .f-item{
    background: rgba(255,255,255,.05); border: 1px solid var(--stroke);
    border-radius: 14px; padding: 10px 12px; font-size: 13.5px; transition:.2s;
  }
  .f-item:hover{ background: rgba(124,92,255,.14); transform: translateY(-2px); }
  .f-item b{ display:block; color: var(--gold); font-size: 13px; margin-bottom: 2px; }
  .f-item code{ color: var(--accent2); font-family: Consolas, monospace; direction: ltr; display:inline-block; font-size: 12.5px; }

  /* Chat */
  .chat-card{ display: flex; flex-direction: column; height: 700px; }
  @media (max-width:950px){ .chat-card{ height: 600px; } }

  .chat-head{
    display:flex; align-items:center; gap:10px;
    padding-bottom: 12px; border-bottom: 1px solid var(--stroke); margin-bottom: 12px;
  }
  .avatar{
    width: 42px; height:42px; border-radius: 14px;
    background: linear-gradient(135deg, var(--accent2), var(--accent));
    display:grid; place-items:center; font-size: 20px;
    box-shadow: 0 6px 18px rgba(124,92,255,.4);
  }
  .chat-head .name{ font-weight: 700; font-size: 15px; }
  .chat-head .status{ font-size: 12px; color: var(--accent2); }
  .chat-head .status::before{ content:"● "; }

  #messages{
    flex: 1; overflow-y: auto; padding: 6px 4px;
    display: flex; flex-direction: column; gap: 10px; scroll-behavior: smooth;
  }
  #messages::-webkit-scrollbar{ width: 6px; }
  #messages::-webkit-scrollbar-thumb{ background: rgba(255,255,255,.15); border-radius: 99px; }

  .msg{
    max-width: 88%; padding: 10px 14px; border-radius: 16px;
    font-size: 13.5px; line-height: 1.9; animation: pop .25s ease;
    word-wrap: break-word;
  }
  @keyframes pop{ from{ opacity:0; transform: translateY(8px);} to{ opacity:1; transform:none;} }
  .msg.bot{
    align-self: flex-start; background: rgba(255,255,255,.08);
    border: 1px solid var(--stroke); border-bottom-right-radius: 4px;
  }
  .msg.user{
    align-self: flex-end;
    background: linear-gradient(135deg, var(--accent), #4a2fd6);
    border-bottom-left-radius: 4px;
  }
  .msg .ltr{ direction: ltr; display: inline-block; font-family: Consolas, monospace; }
  .msg .hl{ color: var(--gold); font-weight: 700; }
  .msg .gr{ color: var(--accent2); font-weight: 600; }

  .typing span{
    display:inline-block; width:7px; height:7px; margin:0 2px;
    background: var(--muted); border-radius:50%;
    animation: bounce 1.2s infinite;
  }
  .typing span:nth-child(2){ animation-delay:.15s; }
  .typing span:nth-child(3){ animation-delay:.3s; }
  @keyframes bounce{ 0%,60%,100%{ transform: translateY(0); opacity:.4;} 30%{ transform: translateY(-6px); opacity:1;} }

  .chips{ display:flex; gap:6px; flex-wrap: wrap; margin-bottom: 10px; }
  .chip{
    background: rgba(255,255,255,.06); border: 1px solid var(--stroke);
    color: var(--muted); font-size: 12px; padding: 5px 11px;
    border-radius: 999px; cursor: pointer; transition: .2s;
  }
  .chip:hover{ background: rgba(124,92,255,.25); color:#fff; border-color: var(--accent); }

  .chat-input{ display:flex; gap:8px; margin-top: 10px; }
  .chat-input input{ flex:1; }
  .chat-input button{ padding: 11px 18px; }

  footer{
    max-width: 1150px; margin: 22px auto 0; text-align: center;
    padding: 18px; border-top: 1px solid var(--stroke);
    color: var(--muted); font-size: 13.5px;
  }
  footer b{
    background: linear-gradient(90deg, var(--gold), var(--accent2));
    -webkit-background-clip:text; background-clip:text; color:transparent;
    font-size: 15px;
  }

  /* tabs for full-width card */
  .full-card{ grid-column: 1 / -1; }
</style>
</head>
<body>

<header>
  <h1>📐 ریاضی فول فول هفتم تا دوازدهم 📐</h1>
  <p class="subtitle">کتابخانه کامل ریاضیات متوسطه — استان فارس</p>
  <div class="badges">
    <div class="badge gold">🏆 بهترین دبیر ریاضی: استاد جوکار</div>
    <div class="badge teal">📍 استان فارس</div>
    <div class="badge">📚 ۶ پایه تحصیلی</div>
    <div class="badge">🤖 دستیار هوشمند متین آرام</div>
  </div>
</header>

<div class="wrap">

  <!-- ===== Tools column ===== -->
  <div>
    <div class="card">
      <h2><span>🧮</span> ابزارهای ریاضی</h2>

      <div class="tool">
        <label>ماشین‌حساب پیشرفته (مثال: 2+3*4 یا 2^10 یا sqrt(144) )</label>
        <div class="row">
          <input type="text" id="calcInput" placeholder="عبارت ریاضی را بنویسید...">
          <button style="flex:0 0 auto" onclick="doCalc()">محاسبه</button>
        </div>
        <div class="result" id="calcResult"></div>
      </div>

      <div class="tool">
        <label>حل معادله درجه دوم &nbsp; ax² + bx + c = 0</label>
        <div class="row">
          <input type="number" id="qa" placeholder="a" step="any">
          <input type="number" id="qb" placeholder="b" step="any">
          <input type="number" id="qc" placeholder="c" step="any">
        </div>
        <button style="width:100%; margin-top:8px" onclick="solveQuad()">حل کن 🔍</button>
        <div class="result" id="quadResult"></div>
      </div>
    </div>

    <div class="card" style="margin-top:18px">
      <h2><span>📚</span> فرمول‌های طلایی (همه پایه‌ها)</h2>
      <div class="formula-grid">
        <div class="f-item"><b>اتحاد مربع</b><code>(a±b)² = a² ± 2ab + b²</code></div>
        <div class="f-item"><b>اتحاد مزدوج</b><code>a² − b² = (a−b)(a+b)</code></div>
        <div class="f-item"><b>اتحاد مکعب</b><code>(a±b)³ = a³ ± 3a²b + 3ab² ± b³</code></div>
        <div class="f-item"><b>اختلاف مکعب</b><code>a³ − b³ = (a−b)(a²+ab+b²)</code></div>
        <div class="f-item"><b>فیثاغورس</b><code>a² + b² = c²</code></div>
        <div class="f-item"><b>مساحت دایره</b><code>S = πr²</code></div>
        <div class="f-item"><b>محیط دایره</b><code>P = 2πr</code></div>
        <div class="f-item"><b>مساحت مثلث</b><code>S = ½ × قاعده × ارتفاع</code></div>
        <div class="f-item"><b>حجم کره</b><code>V = 4/3 πr³</code></div>
        <div class="f-item"><b>حجم استوانه</b><code>V = πr²h</code></div>
        <div class="f-item"><b>دلتا</b><code>Δ = b² − 4ac</code></div>
        <div class="f-item"><b>ریشه معادله</b><code>x = (−b ± √Δ) / 2a</code></div>
        <div class="f-item"><b>مشتق توان</b><code>(xⁿ)′ = n·xⁿ⁻¹</code></div>
        <div class="f-item"><b>مشتق ضرب</b><code>(uv)′ = u′v + uv′</code></div>
        <div class="f-item"><b>مشتق تقسیم</b><code>(u/v)′ = (u′v−uv′)/v²</code></div>
        <div class="f-item"><b>اتحاد مثلثاتی</b><code>sin²θ + cos²θ = 1</code></div>
        <div class="f-item"><b>لگاریتم ضرب</b><code>log(ab) = log a + log b</code></div>
        <div class="f-item"><b>دنباله حسابی</b><code>aₙ = a₁ + (n−1)d</code></div>
        <div class="f-item"><b>دنباله هندسی</b><code>aₙ = a₁ · rⁿ⁻¹</code></div>
        <div class="f-item"><b>احتمال</b><code>P(A) = n(A)/n(S)</code></div>
      </div>
    </div>
  </div>

  <!-- ===== Chat column ===== -->
  <div class="card chat-card">
    <div class="chat-head">
      <div class="avatar">🤖</div>
      <div>
        <div class="name">دستیار ریاضی متین آرام</div>
        <div class="status">آنلاین — مسلط بر ریاضی هفتم تا دوازدهم</div>
      </div>
    </div>

    <div class="chips">
      <div class="chip" onclick="quick('هفتم')">هفتم</div>
      <div class="chip" onclick="quick('هشتم')">هشتم</div>
      <div class="chip" onclick="quick('نهم')">نهم</div>
      <div class="chip" onclick="quick('دهم')">دهم</div>
      <div class="chip" onclick="quick('یازدهم')">یازدهم</div>
      <div class="chip" onclick="quick('دوازدهم')">دوازدهم</div>
      <div class="chip" onclick="quick('مشتق')">مشتق</div>
      <div class="chip" onclick="quick('مثلثات')">مثلثات</div>
      <div class="chip" onclick="quick('حد')">حد</div>
      <div class="chip" onclick="quick('اتحاد')">اتحادها</div>
    </div>

    <div id="messages"></div>

    <div class="chat-input">
      <input type="text" id="chatInput" placeholder="بپرس: مثلا «مثلثات یازدهم» یا «مشتق دوازدهم»..." onkeydown="if(event.key==='Enter') sendMsg()">
      <button onclick="sendMsg()">ارسال ➤</button>
    </div>
  </div>

  <!-- ===== Full-width Grade Browser ===== -->
  <div class="card full-card">
    <h2><span>🎓</span> کتابخانه ریاضی هفتم تا دوازدهم</h2>
    <div class="grade-tabs" id="gradeTabs"></div>
    <div class="grade-content" id="gradeContent"></div>
  </div>

</div>

<footer>
  ساخته شده توسط <b>هوش مصنوعی متین آرام</b> 💜<br>
  ویژه دانش‌آموزان استان فارس | با افتخار برای استاد جوکار 🏆
</footer>

<script>
/* ========== ابزار کمکی ========== */
function toEnDigits(str){
  const fa = '۰۱۲۳۴۵۶۷۸۹', ar = '٠١٢٣٤٥٦٧٨٩';
  return String(str)
    .replace(/[۰-۹]/g, d => fa.indexOf(d))
    .replace(/[٠-٩]/g, d => ar.indexOf(d));
}
function normalizeExpr(str){
  return toEnDigits(str)
    .replace(/×/g, '*').replace(/÷/g, '/')
    .replace(/−/g, '-').replace(/–/g, '-')
    .replace(/\s+/g, '');
}
function safeEval(raw){
  let e = normalizeExpr(raw);
  if(!e) return null;
  e = e.replace(/\^/g, '**');
  const fns = { sqrt:'Math.sqrt', sin:'Math.sin', cos:'Math.cos', tan:'Math.tan',
                log:'Math.log10', ln:'Math.log', abs:'Math.abs', pi:'Math.PI' };
  e = e.replace(/(sqrt|sin|cos|tan|log|ln|abs|pi)/g, m => fns[m]);
  if(!/^[0-9+\-*/().,%\sMathsqrtincoslgabPI]*$/.test(e)) return null;
  try{
    const val = Function('"use strict";return (' + e + ')')();
    if(typeof val !== 'number' || !isFinite(val)) return null;
    return Math.round(val * 1e10) / 1e10;
  }catch{ return null; }
}
function doCalc(){
  const inp = document.getElementById('calcInput').value.trim();
  const out = document.getElementById('calcResult');
  if(!inp){ out.textContent = '⚠️ یک عبارت وارد کن.'; return; }
  const r = safeEval(inp);
  out.textContent = (r === null)
    ? '❌ عبارت نامعتبر است. مثال درست: 2+3*4'
    : `✅ نتیجه:\n${inp} = ${r}`;
}
function solveQuad(){
  const a = parseFloat(toEnDigits(document.getElementById('qa').value));
  const b = parseFloat(toEnDigits(document.getElementById('qb').value));
  const c = parseFloat(toEnDigits(document.getElementById('qc').value));
  const out = document.getElementById('quadResult');
  if([a,b,c].some(v => isNaN(v))){ out.textContent = '⚠️ هر سه ضریب a و b و c را وارد کن.'; return; }
  if(a === 0){ out.textContent = '⚠️ اگر a=0 باشد معادله درجه دوم نیست.'; return; }
  const D = b*b - 4*a*c;
  let txt = `Δ = b² − 4ac = ${D}\n`;
  if(D > 0){
    txt += `✅ دو ریشه حقیقی:\n x₁ = ${rnd((-b+Math.sqrt(D))/(2*a))}\n x₂ = ${rnd((-b-Math.sqrt(D))/(2*a))}`;
  } else if(D === 0){
    txt += `✅ یک ریشه مضاعف:\n x = ${rnd(-b/(2*a))}`;
  } else {
    txt += `✅ ریشه مختلط:\n x = ${rnd(-b/(2*a))} ± ${rnd(Math.sqrt(-D)/(2*a))}i`;
  }
  out.textContent = txt;
}
function rnd(n){ return Math.round(n*10000)/10000; }

/* ============================================================
   کتابخانه کامل ریاضی هفتم تا دوازدهم
   ============================================================ */
const MATH_DB = {
  "هفتم": {
    title: "ریاضی پایه هفتم",
    chapters: [
      { name:"فصل ۱: راهبردهای حل مسئله", topics:["الگوسازی","حل مسئله با رسم شکل","حل مسئله ساده‌تر","زیرمسئله"] },
      { name:"فصل ۲: عددهای صحیح", topics:["جمع و تفریق اعداد صحیح","ضرب و تقسیم اعداد صحیح","قرینه و قدر مطلق","ترتیب انجام عملیات"] },
      { name:"فصل ۳: جبر و معادله", topics:["عبارت‌های جبری","مقدار عددی عبارت","معادله درجه اول","تبدیل و ساده‌سازی"] },
      { name:"فصل ۴: هندسه و استدلال", topics:["زاویه‌ها","مثلث و انواع آن","دو خط موازی","استدلال و اثبات"] },
      { name:"فصل ۵: شمارنده‌ها و اعداد اول", topics:["شمارنده‌ها","اعداد اول","ب.م.م","ک.م.م"] },
      { name:"فصل ۶: سطح و حجم", topics:["مساحت جانبی و کل","حجم منشور و استوانه","تبدیل واحدها"] },
      { name:"فصل ۷: توان و جذر", topics:["قواعد توان","جذر تقریبی","جذر دقیق"] },
      { name:"فصل ۸: بردار و مختصات", topics:["دستگاه مختصات","جمع بردارها","قرینه بردار"] },
      { name:"فصل ۹: آمار و احتمال", topics:["جمع‌آوری داده","نمودارها","میانگین و مد","احتمال ساده"] }
    ]
  },
  "هشتم": {
    title: "ریاضی پایه هشتم",
    chapters: [
      { name:"فصل ۱: عددهای صحیح و گویا", topics:["یادآوری اعداد صحیح","جمع و تفریق گویا","ضرب و تقسیم گویا","حل مسئله"] },
      { name:"فصل ۲: عددهای اول", topics:["شمارنده","ب.م.م و ک.م.م","الگوریتم اقلیدس","مسئله‌های کاربردی"] },
      { name:"فصل ۳: چندضلعی‌ها", topics:["زاویه‌های داخلی و خارجی","چندضلعی منتظم","محیط و مساحت"] },
      { name:"فصل ۴: جبر و معادله", topics:["اتحادهای algebraic","تجزیه عبارت","معادله درجه اول","دستگاه معادلات ساده"] },
      { name:"فصل ۵: بردار و مختصات", topics:["بردار مساوی","مختصات بردار","ضرب عدد در بردار"] },
      { name:"فصل ۶: مثلث", topics:["رابطه فیثاغورس","مثلث‌های متشابه","تالس","هم‌نهشتی"] },
      { name:"فصل ۷: توان و جذر", topics:["توان صحیح","نماد علمی","جذر و رادیکال","گویا کردن مخرج"] },
      { name:"فصل ۸: آمار و احتمال", topics:["نمودار دایره‌ای","میانه و مد","احتمال رخداد"] },
      { name:"فصل ۹: دایره", topics:["زاویه مرکزی و محاطی","خط مماس","وتر و قوس"] }
    ]
  },
  "نهم": {
    title: "ریاضی پایه نهم",
    chapters: [
      { name:"فصل ۱: مجموعه‌ها", topics:["مجموعه و اعضا","زیرمجموعه","اشتراک و اجتماع","متمم"] },
      { name:"فصل ۲: عددهای حقیقی", topics:["اعداد گنگ","اعداد حقیقی","محور اعداد حقیقی","تقریب"] },
      { name:"فصل ۳: استدلال و اثبات", topics:["استدلال استقرایی و استنتاجی","برهان خلف","اثبات در هندسه"] },
      { name:"فصل ۴: توان و ریشه", topics:["توان‌های کسری","رادیکال‌ها","عملیات روی رادیکال","گویا کردن"] },
      { name:"فصل ۵: عبارت‌های جبری", topics:["اتحادهای مهم","تجزیه","عبارت‌های گویا","معادلات کسری"] },
      { name:"فصل ۶: خط و معادله‌های خطی", topics:["شیب خط","معادله خط","دو خط موازی و عمود","دستگاه دو معادله"] },
      { name:"فصل ۷: عبارت‌های گنگ", topics:["ساده کردن","عملیات","معادله گنگ"] },
      { name:"فصل ۸: حجم و مساحت", topics:["حجم هرم و مخروط","مساحت جانبی","کره"] },
      { name:"فصل ۹: دوران و تقارن", topics:["تقارن محوری و مرکزی","دوران","تجانس"] }
    ]
  },
  "دهم": {
    title: "ریاضی پایه دهم (رشته ریاضی و تجربی)",
    chapters: [
      { name:"فصل ۱: مجموعه، الگو و دنباله", topics:["مجموعه‌ها","دنباله حسابی","دنباله هندسی","رابطه بازگشتی"] },
      { name:"فصل ۲: مثلثات", topics:["نسبت‌های مثلثاتی","دایره مثلثاتی","رادیان","اتحادهای مثلثاتی"] },
      { name:"فصل ۳: توان‌های گویا", topics:["توان کسری","رادیکال","عبارت‌های جبری","اتحادها"] },
      { name:"فصل ۴: معادله‌ها و نامعادله‌ها", topics:["معادله درجه دوم","نامعادله","قدرمطلق","دستگاه معادلات"] },
      { name:"فصل ۵: تابع", topics:["مفهوم تابع","دامنه و برد","تابع خطی","تابع درجه دوم"] },
      { name:"فصل ۶: شمارش، بدون شمردن", topics:["اصل شمارش","جایگشت","ترکیب","فاکتوریل"] },
      { name:"فصل ۷: آمار و احتمال", topics:["شاخص‌های آماری","احتمال","احتمال شرطی"] }
    ]
  },
  "یازدهم": {
    title: "ریاضی پایه یازدهم",
    chapters: [
      { name:"فصل ۱: هندسه تحلیلی و جبر", topics:["معادله خط","دایره","مقاطع مخروطی","بردار در فضا"] },
      { name:"فصل ۲: تابع", topics:["توابع خاص","تابع یک‌به‌یک","تابع معکوس","ترکیب توابع"] },
      { name:"فصل ۳: مثلثات", topics:["توابع مثلثاتی","اتحادهای مثلثاتی","معادلات مثلثاتی","نمودار سینوس و کسینوس"] },
      { name:"فصل ۴: حد و پیوستگی", topics:["مفهوم حد","حد یک‌طرفه","حد بی‌نهایت","پیوستگی"] },
      { name:"فصل ۵: مشتق", topics:["مفهوم مشتق","قواعد مشتق","مشتق ضرب و تقسیم","مشتق زنجیره‌ای"] },
      { name:"فصل ۶: آمار و احتمال", topics:["متغیر تصادفی","امید ریاضی","توزیع دوجمله‌ای","احتمال شرطی"] }
    ]
  },
  "دوازدهم": {
    title: "ریاضی پایه دوازدهم",
    chapters: [
      { name:"فصل ۱: تابع", topics:["توابع چندجمله‌ای","تابع نمایی","تابع لگاریتمی","معادلات نمایی و لگاریتمی"] },
      { name:"فصل ۲: مثلثات", topics:["توابع مثلثاتی","معادلات مثلثاتی","نمودارها","کاربردها"] },
      { name:"فصل ۳: حد", topics:["حد توابع","حد بی‌نهایت","حد در بی‌نهایت","فرم‌های مبهم"] },
      { name:"فصل ۴: مشتق", topics:["قواعد مشتق","مشتق توابع مثلثاتی","مشتق نمایی و لگاریتمی","مشتق مرتبه بالا"] },
      { name:"فصل ۵: کاربرد مشتق", topics:["صعودی و نزولی","اکسترمم","بهینه‌سازی","رسم نمودار"] },
      { name:"فصل ۶: هندسه", topics:["تشابه","قضیه تالس","دایره و مماس","فضا"] },
      { name:"فصل ۷: احتمال", topics:["احتمال شرطی","پیشامد مستقل","قانون بیز"] },
      { name:"فصل ۸: ریاضیات مالی (تجربی)", topics:["سود و زیان","ارزش فعلی","وام و اقساط"] }
    ]
  }
};

/* ========== ساخت تب‌های پایه ========== */
const gradeTabsEl = document.getElementById('gradeTabs');
const gradeContentEl = document.getElementById('gradeContent');
const gradeNames = Object.keys(MATH_DB);
let activeGrade = 'هفتم';

function renderTabs(){
  gradeTabsEl.innerHTML = '';
  gradeNames.forEach(g => {
    const btn = document.createElement('button');
    btn.className = 'gtab' + (g === activeGrade ? ' active' : '');
    btn.textContent = g;
    btn.onclick = () => { activeGrade = g; renderTabs(); renderGrade(); };
    gradeTabsEl.appendChild(btn);
  });
}

function renderGrade(){
  const data = MATH_DB[activeGrade];
  if(!data){ gradeContentEl.innerHTML = ''; return; }
  let html = `<div class="grade-title">📘 ${data.title}</div>`;
  data.chapters.forEach(ch => {
    html += `<div class="chapter"><b>${ch.name}</b><ul>`;
    ch.topics.forEach(t => { html += `<li>${t}</li>`; });
    html += `</ul></div>`;
  });
  gradeContentEl.innerHTML = html;
}

renderTabs();
renderGrade();

/* ========== چت ========== */
const messages = document.getElementById('messages');

function escapeHTML(s){
  return s.replace(/[&<>"']/g, c => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
}
function addMsg(text, who){
  const div = document.createElement('div');
  div.className = 'msg ' + who;
  div.innerHTML = escapeHTML(text).replace(/\n/g, '<br>');
  messages.appendChild(div);
  messages.scrollTop = messages.scrollHeight;
}
function addTyping(){
  const div = document.createElement('div');
  div.className = 'msg bot typing';
  div.innerHTML = '<span></span><span></span><span></span>';
  messages.appendChild(div);
  messages.scrollTop = messages.scrollHeight;
  return div;
}

/* ==== پایگاه دانش کامل ==== */
const TOPIC_ANSWERS = [
  // ===== هفتم =====
  { keys:["هفتم","پایه هفتم","ریاضی هفتم"], grade:true, ans:() => gradeReply('هفتم') },
  { keys:["عدد صحیح","اعداد صحیح"], ans: () =>
    "🔢 <span class='hl'>اعداد صحیح (هفتم)</span>\n" +
    "• شامل: ...-2, -1, 0, 1, 2,...\n" +
    "• جمع: هم‌علامت → جمع و حفظ علامت | مختلف‌العلامت → تفریق و علامت بزرگ‌تر\n" +
    "• ضرب/تقسیم: (−)×(−)=(+) | (−)×(+)=(−)\n" +
    "• قرینه: عدد با علامت مخالف\n" +
    "• قدر مطلق: فاصله از صفر (همیشه ≥ 0)" },
  { keys:["ک.م.م","ک م م","کوچکترین مضرب"], ans: () =>
    "🔗 <span class='hl'>ک.م.م (کمترین مضرب مشترک)</span>\n" +
    "• تجزیه به عامل‌های اول\n" +
    "• هر عامل با <b>بزرگترین توان</b> ضرب می‌شود\n" +
    "مثال: ک.م.م(12, 18) = 2²×3² = 36" },
  { keys:["ب.م.م","ب م م","بزرگترین مقسوم"], ans: () =>
    "🔗 <span class='hl'>ب.م.م (بزرگترین مقسوم‌علیه مشترک)</span>\n" +
    "• تجزیه به عامل‌های اول\n" +
    "• عامل‌های <b>مشترک</b> با <b>کوچکترین توان</b>\n" +
    "مثال: ب.م.م(12, 18) = 2×3 = 6" },
  { keys:["جذر","رادیکال"], ans: () =>
    "√ <span class='hl'>جذر و رادیکال (هفتم تا نهم)</span>\n" +
    "• جذر دقیق: √25 = 5\n" +
    "• جذر تقریبی: بین دو عدد صحیح\n" +
    "• قواعد: √(a×b) = √a × √b\n" +
    "• گویا کردن مخرج: ضرب در مزدوج\n" +
    "مثال: 1/√2 = √2/2" },
  { keys:["توان"], ans: () =>
    "⚡ <span class='hl'>توان (هفتم تا نهم)</span>\n" +
    "• aⁿ = a×a×...×a (n بار)\n" +
    "• aᵐ × aⁿ = aᵐ⁺ⁿ\n" +
    "• aᵐ ÷ aⁿ = aᵐ⁻ⁿ\n" +
    "• (aᵐ)ⁿ = aᵐⁿ\n" +
    "• a⁰ = 1 (a≠0) ، a⁻ⁿ = 1/aⁿ" },

  // ===== هشتم =====
  { keys:["هشتم","پایه هشتم","ریاضی هشتم"], grade:true, ans:() => gradeReply('هشتم') },
  { keys:["اتحاد","اتحادها","اتحاد جبری"], ans: () =>
    "🧩 <span class='hl'>اتحادهای مهم (هشتم تا دوازدهم)</span>\n" +
    "• (a+b)² = a² + 2ab + b²\n" +
    "• (a−b)² = a² − 2ab + b²\n" +
    "• (a+b)(a−b) = a² − b²\n" +
    "• (a+b)³ = a³ + 3a²b + 3ab² + b³\n" +
    "• (a−b)³ = a³ − 3a²b + 3ab² − b³\n" +
    "• a³+b³ = (a+b)(a²−ab+b²)\n" +
    "• a³−b³ = (a−b)(a²+ab+b²)" },
  { keys:["فیثاغورس","وتر"], ans: () =>
    "📐 <span class='hl'>قضیه فیثاغورس (هشتم)</span>\n" +
    "در مثلث قائم‌الزاویه: a² + b² = c²\n" +
    "• c: وتر (ضلع مقابل زاویه ۹۰°)\n" +
    "• عکس فیثاغورس: اگر a²+b²=c² → مثلث قائم است\n" +
    "مثال: 3-4-5 ✅ ، 5-12-13 ✅ ، 8-15-17 ✅" },
  { keys:["تالس","قضیه تالس"], ans: () =>
    "📏 <span class='hl'>قضیه تالس (هشتم و دوازدهم)</span>\n" +
    "اگر دو خط موازی، دو ضلع مثلث را قطع کنند:\n" +
    "AD/DB = AE/EC\n" +
    "یا: خطوط موازی، پاره‌های متناسب روی دو خط ایجاد می‌کنند." },
  { keys:["دایره","زاویه مرکزی","زاویه محاطی","مماس"], ans: () =>
    "⭕ <span class='hl'>دایره (هشتم و دوازدهم)</span>\n" +
    "• زاویه مرکزی = ۲ × زاویه محاطی (روی یک کمان)\n" +
    "• زاویه محاطی مقابل قطر = ۹۰°\n" +
    "• مماس ⊥ شعاع در نقطه تماس\n" +
    "• محیط = ۲πr ، مساحت = πr²" },

  // ===== نهم =====
  { keys:["نهم","پایه نهم","ریاضی نهم"], grade:true, ans:() => gradeReply('نهم') },
  { keys:["مجموعه","مجموعه‌ها"], ans: () =>
    "🗂 <span class='hl'>مجموعه‌ها (نهم و دهم)</span>\n" +
    "• A∪B: اجتماع (همه اعضا)\n" +
    "• A∩B: اشتراک (اعضای مشترک)\n" +
    "• A−B: تفاضل\n" +
    "• A': متمم نسبت به مجموعه مرجع\n" +
    "• ∅: مجموعه تهی" },
  { keys:["گنگ","عدد گنگ","اصم"], ans: () =>
    "🔢 <span class='hl'>اعداد گنگ (نهم)</span>\n" +
    "• اعشاری نامتناهی و غیرتکرارشونده\n" +
    "• مثال: √2, √3, π, e\n" +
    "• مجموعه اعداد حقیقی = گویا ∪ گنگ" },
  { keys:["استدلال","اثبات","برهان"], ans: () =>
    "🧠 <span class='hl'>استدلال و اثبات (نهم)</span>\n" +
    "• استدلال استقرایی: از جزئی به کلی\n" +
    "• استدلال استنتاجی: از کلی به جزئی\n" +
    "• برهان خلف: فرض خلاف → تناقض\n" +
    "• اثبات مستقیم: زنجیره استدلال منطقی" },
  { keys:["شیب","معادله خط","خط راست"], ans: () =>
    "📈 <span class='hl'>خط و معادله خطی (نهم و یازدهم)</span>\n" +
    "• شیب: m = (y₂−y₁)/(x₂−x₁)\n" +
    "• معادله خط: y = mx + b\n" +
    "• دو خط موازی: m₁ = m₂\n" +
    "• دو خط عمود: m₁×m₂ = −1\n" +
    "• فرم کلی: ax + by + c = 0" },

  // ===== دهم =====
  { keys:["دهم","پایه دهم","ریاضی دهم"], grade:true, ans:() => gradeReply('دهم') },
  { keys:["دنباله","دنباله حسابی","دنباله هندسی"], ans: () =>
    "🔗 <span class='hl'>دنباله‌ها (دهم)</span>\n" +
    "• حسابی: aₙ = a₁ + (n−1)d\n" +
    "  مجموع: Sₙ = n/2 × (a₁ + aₙ)\n" +
    "• هندسی: aₙ = a₁ · rⁿ⁻¹\n" +
    "  مجموع: Sₙ = a₁(1−rⁿ)/(1−r)  (r≠1)\n" +
    "• رابطه بازگشتی: هر جمله از جملات قبل" },
  { keys:["مثلثات","سینوس","کسینوس","تانژانت"], ans: () =>
    "🔺 <span class='hl'>مثلثات (دهم، یازدهم، دوازدهم)</span>\n" +
    "• sin = مقابل/وتر ، cos = مجاور/وتر ، tan = sin/cos\n" +
    "• اتحاد اصلی: sin²θ + cos²θ = 1\n" +
    "• sin(α±β) = sinα·cosβ ± cosα·sinβ\n" +
    "• cos(α±β) = cosα·cosβ ∓ sinα·sinβ\n" +
    "• sin2α = 2sinα·cosα\n" +
    "• cos2α = cos²α − sin²α\n" +
    "• زوایای مهم: sin30=½ ، sin45=√2/2 ، sin60=√3/2" },
  { keys:["رادیان","درجه"], ans: () =>
    "🔄 <span class='hl'>رادیان و درجه</span>\n" +
    "• π رادیان = 180°\n" +
    "• 1 رادیان ≈ 57.3°\n" +
    "• 30° = π/6 ، 45° = π/4 ، 60° = π/3 ، 90° = π/2\n" +
    "• تبدیل: درجه × π/180 = رادیان" },
  { keys:["تابع","دامنه","برد"], ans: () =>
    "🔧 <span class='hl'>تابع (دهم، یازدهم، دوازدهم)</span>\n" +
    "• تابع: هر عضو دامنه دقیقاً یک عضو برد دارد\n" +
    "• دامنه: ورودی‌های مجاز ، برد: خروجی‌ها\n" +
    "• تابع خطی: y = ax + b\n" +
    "• تابع درجه دوم: y = ax² + bx + c\n" +
    "  رأس: x = −b/2a" },
  { keys:["معادله درجه دوم","درجه دوم","دلتا"], ans: () =>
    "🧮 <span class='hl'>معادله درجه دوم (دهم)</span>\n" +
    "ax² + bx + c = 0\n" +
    "• Δ = b² − 4ac\n" +
    "• Δ>0: دو ریشه حقیقی\n" +
    "• Δ=0: یک ریشه مضاعف\n" +
    "• Δ<0: دو ریشه مختلط\n" +
    "• x = (−b ± √Δ) / 2a\n" +
    "• مجموع ریشه‌ها: −b/a ، حاصلضرب: c/a" },
  { keys:["قدرمطلق","قدر مطلق"], ans: () =>
    "|x| <span class='hl'>قدر مطلق (دهم)</span>\n" +
    "• |x| = x اگر x≥0 ، |x| = −x اگر x<0\n" +
    "• |x| = a → x = a یا x = −a (a≥0)\n" +
    "• |x| < a → −a < x < a\n" +
    "• |x| > a → x < −a یا x > a" },
  { keys:["جایگشت","ترکیب","فاکتوریل","شمارش"], ans: () =>
    "🎲 <span class='hl'>شمارش (دهم)</span>\n" +
    "• اصل ضرب: اگر m راه و n راه → m×n\n" +
    "• فاکتوریل: n! = n×(n−1)×...×1\n" +
    "• جایگشت (ترتیب مهم): P(n,r) = n!/(n−r)!\n" +
    "• ترکیب (ترتیب مهم نیست): C(n,r) = n!/(r!(n−r)!)" },
  { keys:["احتمال"], ans: () =>
    "🎯 <span class='hl'>احتمال (همه پایه‌ها)</span>\n" +
    "• P(A) = تعداد حالات مطلوب / کل حالات\n" +
    "• 0 ≤ P(A) ≤ 1\n" +
    "• P(A') = 1 − P(A)\n" +
    "• P(A∪B) = P(A) + P(B) − P(A∩B)\n" +
    "• مستقل: P(A∩B) = P(A)·P(B)\n" +
    "• شرطی: P(A|B) = P(A∩B)/P(B)" },

  // ===== یازدهم =====
  { keys:["یازدهم","پایه یازدهم","ریاضی یازدهم"], grade:true, ans:() => gradeReply('یازدهم') },
  { keys:["حد","حد و پیوستگی","پیوستگی"], ans: () =>
    "➡️ <span class='hl'>حد و پیوستگی (یازدهم و دوازدهم)</span>\n" +
    "• lim(x→a) f(x) = L\n" +
    "• حد چپ = حد راست → حد وجود دارد\n" +
    "• فرم‌های مبهم: 0/0 ، ∞/∞\n" +
    "• روش‌ها: تجزیه، هم‌مخرج، هوپیتال\n" +
    "• پیوستگی در a: f(a) تعریف شده و lim f(x) = f(a)\n" +
    "• حدهای مهم: lim(sinx/x) = 1 ، lim((1+1/n)ⁿ) = e" },
  { keys:["مشتق","قواعد مشتق","مشتق‌گیری"], ans: () =>
    "📈 <span class='hl'>مشتق (یازدهم و دوازدهم)</span>\n" +
    "• تعریف: f'(x) = lim(h→0) [f(x+h)−f(x)]/h\n" +
    "• (c)' = 0\n" +
    "• (xⁿ)' = n·xⁿ⁻¹\n" +
    "• (sinx)' = cosx ، (cosx)' = −sinx\n" +
    "• (tanx)' = 1/cos²x\n" +
    "• (eˣ)' = eˣ ، (aˣ)' = aˣ·lna\n" +
    "• (lnx)' = 1/x\n" +
    "• ضرب: (uv)' = u'v + uv'\n" +
    "• تقسیم: (u/v)' = (u'v − uv')/v²\n" +
    "• زنجیره‌ای: [f(g(x))]' = f'(g(x))·g'(x)" },
  { keys:["هندسه تحلیلی","مقاطع مخروطی","بیضی","سهمی","هذلولی"], ans: () =>
    "📐 <span class='hl'>مقاطع مخروطی (یازدهم)</span>\n" +
    "• دایره: (x−a)² + (y−b)² = r²\n" +
    "• سهمی: y² = 2px (کانون روی محور)\n" +
    "• بیضی: x²/a² + y²/b² = 1\n" +
    "  کانون‌ها: (±c, 0) ، c² = a² − b²\n" +
    "• هذلولی: x²/a² − y²/b² = 1\n" +
    "  کانون‌ها: (±c, 0) ، c² = a² + b²" },
  { keys:["معکوس تابع","تابع معکوس"], ans: () =>
    "🔄 <span class='hl'>تابع معکوس (یازدهم)</span>\n" +
    "• شرط: تابع یک‌به‌یک باشد\n" +
    "• y = f(x) → x = f⁻¹(y)\n" +
    "• نمودار معکوس: قرینه نسبت به y=x\n" +
    "• دامنه f⁻¹ = برد f ، برد f⁻¹ = دامنه f" },

  // ===== دوازدهم =====
  { keys:["دوازدهم","پایه دوازدهم","ریاضی دوازدهم"], grade:true, ans:() => gradeReply('دوازدهم') },
  { keys:["اکسترمم","صعودی","نزولی","بهینه"], ans: () =>
    "⛰ <span class='hl'>کاربرد مشتق (دوازدهم)</span>\n" +
    "• f'>0 → صعودی ، f'<0 → نزولی\n" +
    "• نقاط بحرانی: f'=0 یا f' موجود نباشد\n" +
    "• آزمون مشتق دوم:\n" +
    "  f''(x₀)>0 → مینیمم\n" +
    "  f''(x₀)<0 → ماکسیمم\n" +
    "• بهینه‌سازی: پیدا کردن max یا min در مسئله" },
  { keys:["لگاریتم","log","ln"], ans: () =>
    "🔢 <span class='hl'>لگاریتم (دوازدهم)</span>\n" +
    "• logₐx = y ⇔ aʸ = x\n" +
    "• log(ab) = loga + logb\n" +
    "• log(a/b) = loga − logb\n" +
    "• log(aⁿ) = n·loga\n" +
    "• logₐa = 1 ، logₐ1 = 0\n" +
    "• تغییر پایه: logₐb = logb/loga\n" +
    "• ln = لگاریتم در پایه e" },
  { keys:["نمایی","تابع نمایی","معادله نمایی"], ans: () =>
    "📈 <span class='hl'>تابع نمایی (دوازدهم)</span>\n" +
    "• f(x) = aˣ (a>0, a≠1)\n" +
    "• اگر a>1: صعودی ، اگر 0<a<1: نزولی\n" +
    "• مشتق: (eˣ)' = eˣ ، (aˣ)' = aˣ·lna\n" +
    "• معادله نمایی: aˣ = aʸ → x=y" },
  { keys:["احتمال شرطی","بیز","پیشامد مستقل"], ans: () =>
    "🎲 <span class='hl'>احتمال پیشرفته (دوازدهم)</span>\n" +
    "• شرطی: P(A|B) = P(A∩B)/P(B)\n" +
    "• مستقل: P(A∩B) = P(A)·P(B)\n" +
    "• قانون بیز: P(A|B) = P(B|A)·P(A)/P(B)\n" +
    "• احتمال کل: P(B) = Σ P(B|Aᵢ)·P(Aᵢ)" },
  { keys:["تشابه","مثلث متشابه"], ans: () =>
    "🔷 <span class='hl'>تشابه مثلث‌ها (دوازدهم)</span>\n" +
    "• دو مثلث متشابه: زوایای برابر و اضلاع متناسب\n" +
    "• حالت‌ها: AA ، SAS ، SSS\n" +
    "• نسبت مساحت‌ها = مربع نسبت تشابه\n" +
    "• نسبت حجم‌ها = مکعب نسبت تشابه" },

  // ===== کلی =====
  { keys:["سلام","درود","hi","hello"], ans:() =>
    "سلام و درود! 🌟\nمن دستیار ریاضی «متین آرام» هستم.\nمسلط بر ریاضی <span class='hl'>هفتم تا دوازدهم</span> هستم.\n\nبپرس:\n• «هفتم» یا «دهم» یا «دوازدهم»\n• یا موضوع: مشتق، مثلثات، حد، لگاریتم، اتحاد، احتمال و...\n• یا یک عبارت عددی: 15*15+20" },
  { keys:["متین","سازنده","کی ساختی"], ans:() =>
    "🦾 من توسط «هوش مصنوعی <span class='hl'>متین آرام</span>» ساخته شده‌ام.\nهدفم آموزش کامل ریاضی هفتم تا دوازدهم برای دانش‌آموزان استان فارسه!" },
  { keys:["جوکار","استاد جوکار"], ans:() =>
    "🏆 <span class='hl'>استاد جوکار</span>، بهترین دبیر ریاضی استان فارس!\nروش تدریس: ساده، عمیق، مفهومی — از هفتم تا کنکور.\nبا استاد جوکار ریاضی رو «فول فول» می‌کنی! 💪" },
  { keys:["فارس","شیراز"], ans:() =>
    "📍 این مجموعه ویژه دانش‌آموزان استان فارس طراحی شده.\nهدف: آموزش ریاضی فول فول با بهترین دبیر، استاد جوکار. 🎯" },
  { keys:["کمک","راهنما","چیکار"], ans:() =>
    "🤝 چطور کمکت کنم؟\n" +
    "• اسم یک پایه: هفتم، هشتم، نهم، دهم، یازدهم، دوازدهم\n" +
    "• موضوع: مشتق، حد، مثلثات، لگاریتم، اتحاد، احتمال، تابع و...\n" +
    "• عبارت عددی: 25*4+10\n\nمنتظرم! 😊" }
];

function gradeReply(grade){
  const data = MATH_DB[grade];
  if(!data) return 'پایه یافت نشد.';
  let txt = `📘 <span class='hl'>${data.title}</span>\n\n`;
  data.chapters.forEach((ch, i) => {
    txt += `${i+1}) <span class='gr'>${ch.name}</span>\n   ${ch.topics.slice(0,4).join(" • ")}\n`;
  });
  txt += `\n👉 در پایین همین صفحه روی تب «${grade}» کلیک کن تا لیست کامل فصل‌ها رو ببینی.`;
  return txt;
}

function getAnswer(raw){
  const t = toEnDigits(raw).trim();
  const q = t.replace(/[؟?!.،؛]/g,'').toLowerCase();

  // ۱) تشخیص پایه
  for(const g of gradeNames){
    if(q === g || q.includes(g + ' ') || q.includes('پایه ' + g) || q.includes('ریاضی ' + g)){
      return gradeReply(g);
    }
  }

  // ۲) تطبیق با کلیدواژه‌ها (طولانی‌ترها اول)
  const sorted = [...TOPIC_ANSWERS].sort((a,b) =>
    Math.max(...b.keys.map(k=>k.length)) - Math.max(...a.keys.map(k=>k.length))
  );
  for(const item of sorted){
    for(const k of item.keys){
      if(q.includes(k.toLowerCase())){
        return item.ans();
      }
    }
  }

  // ۳) تلاش برای محاسبه
  const calc = safeEval(t);
  if(calc !== null && /[0-9]/.test(t) && /[+\-*/^%]/.test(t)){
    return `🧮 محاسبه:\n${t} = ${calc}\n\n✅ حل شد! سؤال بعدی؟`;
  }

  // ۴) پیش‌فرض
  return '🤔 این را دقیق متوجه نشدم.\n' +
         'می‌تونی این‌ها را امتحان کنی:\n' +
         '• «هفتم» ، «هشتم» ، ... ، «دوازدهم»\n' +
         '• «مشتق» ، «حد» ، «مثلثات» ، «لگاریتم»\n' +
         '• «اتحاد» ، «احتمال» ، «تابع» ، «دنباله»\n' +
         '• یا یک عبارت مثل: 25*4+10';
}

function sendMsg(){
  const input = document.getElementById('chatInput');
  const text = input.value.trim();
  if(!text) return;
  addMsg(text, 'user');
  input.value = '';
  const typing = addTyping();
  setTimeout(() => {
    typing.remove();
    addMsg(getAnswer(text), 'bot');
  }, 450 + Math.random() * 350);
}

function quick(t){
  document.getElementById('chatInput').value = t;
  sendMsg();
}

/* پیام خوش‌آمد */
window.addEventListener('load', () => {
  addMsg('سلام! 👋 من دستیار هوشمند ریاضی «متین آرام» هستم.\n' +
         '📚 مسلط بر ریاضی <span class="hl">هفتم تا دوازدهم</span>\n' +
         'ویژه دانش‌آموزان استان فارس — با افتخار کنار استاد جوکار 🏆\n\n' +
         'بپرس: «دهم» ، «مشتق» ، «مثلثات» ، «حد» ، «لگاریتم» ، یا یک محاسبه مثل 25*4+10', 'bot');
});
</script>
</body>
</html>
