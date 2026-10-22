<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>ZIAD GLOW UP</title>
<style>
:root {
  --bg:#0c110e;
  --card:#151e19;
  --green:#9be7b2;
  --text:#f2f7f3;
  --muted:#a7b7ac;
}
* { box-sizing:border-box; }
body {
  margin:0;
  background:var(--bg);
  color:var(--text);
  font-family:Arial,Tahoma,sans-serif;
  line-height:1.8;
}
.container {
  max-width:900px;
  margin:auto;
  padding:20px;
}
header, section {
  background:var(--card);
  border:1px solid #2c3c32;
  border-radius:18px;
  padding:20px;
  margin-bottom:16px;
}
header {
  background:linear-gradient(135deg,#1c3023,#111914);
}
h1 span, h2 { color:var(--green); }
p { color:var(--muted); }
input, textarea {
  width:100%;
  padding:12px;
  margin:7px 0;
  background:#0c110e;
  color:white;
  border:1px solid #385541;
  border-radius:10px;
}
button {
  padding:11px 16px;
  border:0;
  border-radius:10px;
  background:var(--green);
  color:#102016;
  font-weight:bold;
  cursor:pointer;
}
.task {
  display:flex;
  gap:10px;
  align-items:center;
  padding:8px 0;
}
.task input { width:20px; }
.task label { flex:1; }
.done label {
  text-decoration:line-through;
  color:var(--muted);
}
.progress {
  height:9px;
  background:#29372e;
  border-radius:10px;
  overflow:hidden;
}
#bar {
  width:0;
  height:100%;
  background:var(--green);
  transition:width .2s;
}
.idea {
  padding:10px;
  margin:7px 0;
  border:1px solid #385541;
  border-radius:10px;
}
small { color:var(--muted); }
</style>
</head>
<body>
<div class="container">

<header>
  <p>YOUR PERSONAL EVOLUTION SYSTEM</p>
  <h1>ZIAD <span>GLOW UP</span></h1>
  <h2>ابنِ نفسك خطوة بخطوة.</h2>
  <p>انضباط، دراسة، صحة، ثقة بالنفس وصناعة المحتوى.</p>
  <p id="date"></p>
</header>

<section>
  <h2>☀️ أهداف اليوم</h2>
  <p>إنجازك: <span id="count">0/5</span></p>
  <div class="progress"><div id="bar"></div></div>

  <div id="tasks">
    <div class="task"><input type="checkbox"><label>مراجعة دروسي لمدة 25 دقيقة</label></div>
    <div class="task"><input type="checkbox"><label>تعلم مهارة لصناعة المحتوى</label></div>
    <div class="task"><input type="checkbox"><label>كتابة فكرة فيديو جديدة</label></div>
    <div class="task"><input type="checkbox"><label>الحركة أو المشي حسب استطاعتي</label></div>
    <div class="task"><input type="checkbox"><label>الاستعداد للنوم في وقت مناسب</label></div>
  </div>
  <p id="message">ابدأ بمهمة واحدة فقط.</p>
</section>

<section>
  <h2>🎬 استوديو صناعة المحتوى</h2>
  <label for="idea">فكرة الفيديو:</label>
  <textarea id="idea" rows="3" placeholder="مثلاً: رحلتي في بناء نفسي بعمر 15 سنة"></textarea>

  <label for="step">أصغر خطوة لتنفيذ الفكرة:</label>
  <input id="step" placeholder="كتابة المقدمة أو تصوير تجربة...">

  <button onclick="saveCreator()">حفظ الفكرة</button>
  <p id="creatorMessage"></p>
</section>

<section>
  <h2>🌱 عاداتي اليومية</h2>
  <div id="habits">
    <div class="task"><input type="checkbox"><label>شرب الماء بانتظام</label></div>
    <div class="task"><input type="checkbox"><label>العناية اللطيفة بالبشرة</label></div>
    <div class="task"><input type="checkbox"><label>خمس دقائق للاسترخاء أو الكتابة</label></div>
  </div>
</section>

<section>
  <h2>🧠 بناء الثقة بالنفس</h2>
  <div class="task"><input type="checkbox"><label>إلقاء السلام على شخص</label></div>
  <div class="task"><input type="checkbox"><label>التحدث مع شخص أشعر بالراحة معه</label></div>
  <div class="task"><input type="checkbox"><label>تصوير فيديو تجريبي لنفسي</label></div>
  <p>تقدم بالتدريج، ولا تجبر نفسك على مواقف تفوق قدرتك. إذا كان الخوف يؤثر على حياتك، اطلب الدعم من شخص بالغ تثق به أو مختص.</p>
</section>

<section>
  <h2>🩺 صحتي</h2>
  <p>فقر الدم يحتاج متابعة طبية. لا تغيّر العلاج أو تبدأ المكملات من تلقاء نفسك.</p>
  <p>للبشرة: تجنب الفرك القاسي وعصر الحبوب، واطلب نصيحة مختص إذا استمرت المشكلة.</p>
  <textarea id="health" rows="3" placeholder="ملاحظات أريد مناقشتها مع ولي أمري أو الطبيب"></textarea>
  <button onclick="saveHealth()">حفظ الملاحظة</button>
</section>

<section>
  <h2>🌙 مراجعة نهاية اليوم</h2>
  <label>ما الشيء الذي أنجزته اليوم؟</label>
  <textarea id="win" rows="2"></textarea>

  <label>ما الذي عطّلني؟</label>
  <textarea id="problem" rows="2"></textarea>

  <label>أهم خطوة للغد:</label>
  <textarea id="tomorrow" rows="2"></textarea>

  <button onclick="saveReview()">حفظ المراجعة</button>
  <button onclick="exportData()">تصدير بياناتي</button>
  <p id="reviewMessage"></p>
</section>

<footer><p>ZIAD GLOW UP · الاستمرارية أهم من الكمال</p></footer>
</div>

<script>
const $ = id => document.getElementById(id);
const storageKey = "ziadGlowUpSimple";

$("date").textContent = new Date().toLocaleDateString("ar-DZ", {
  weekday:"long", year:"numeric", month:"long", day:"numeric"
});

let data = {};
try {
  data = JSON.parse(localStorage.getItem(storageKey) || "{}");
} catch(e) {
  data = {};
}

function persist() {
  localStorage.setItem(storageKey, JSON.stringify(data));
}

function updateTasks() {
  const boxes = [...document.querySelectorAll("#tasks input")];
  const done = boxes.filter(box => box.checked).length;

  $("count").textContent = done + "/" + boxes.length;
  $("bar").style.width = (done / boxes.length * 100) + "%";

  $("message").textContent = done === boxes.length
    ? "أكملت مهام اليوم. أحسنت!"
    : done >= 3
    ? "تقدم جيد. واصل حسب طاقتك."
    : "خطوة صغيرة اليوم أفضل من التأجيل.";

  boxes.forEach(box => {
    box.parentElement.classList.toggle("done", box.checked);
  });

  data.tasks = boxes.map(box => box.checked);
  persist();
}

document.querySelectorAll("#tasks input").forEach(box => {
  box.addEventListener("change", updateTasks);
});

function saveCreator() {
  data.idea = $("idea").value;
  data.step = $("step").value;
  persist();
  $("creatorMessage").textContent = "تم حفظ فكرتك على هذا المتصفح.";
}

function saveHealth() {
  data.health = $("health").value;
  persist();
  alert("تم حفظ الملاحظة.");
}

function saveReview() {
  data.review = {
    win: $("win").value,
    problem: $("problem").value,
    tomorrow: $("tomorrow").value
  };
  persist();
  $("reviewMessage").textContent = "تم حفظ مراجعتك.";
}

function exportData() {
  const file = new Blob(
    [JSON.stringify(data, null, 2)],
    {type:"application/json"}
  );
  const url = URL.createObjectURL(file);
  const a = document.createElement("a");
  a.href = url;
  a.download = "ziad-glow-up-data.json";
  a.click();
  URL.revokeObjectURL(url);
}

function loadData() {
  $("idea").value = data.idea || "";
  $("step").value = data.step || "";
  $("health").value = data.health || "";

  if (data.review) {
    $("win").value = data.review.win || "";
    $("problem").value = data.review.problem || "";
    $("tomorrow").value = data.review.tomorrow || "";
  }

  const boxes = [...document.querySelectorAll("#tasks input")];
  (data.tasks || []).forEach((checked, i) => {
    if (boxes[i]) boxes[i].checked = checked;
  });

  const habits = [...document.querySelectorAll("#habits input")];
  (data.habits || []).forEach((checked, i) => {
    if (habits[i]) habits[i].checked = checked;
  });

  habits.forEach(box => {
    box.addEventListener("change", () => {
      data.habits = habits.map(item => item.checked);
      persist();
    });
  });

  updateTasks();
}

loadData();
</script>
</body>
</html>
