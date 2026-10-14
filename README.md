# glow-up-ai
Glow Up AI - Your personalized beauty and lifestyle experience
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#fff5f7">
<title>Glow Up AI | Your Glow-Up, Your Rules</title>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  background: #fffaf9;
  color: #45363a;
}

header {
  padding: 22px 18px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #fff;
  border-bottom: 1px solid #f4e6e8;
}

.logo {
  font-family: Georgia, serif;
  font-size: 24px;
  color: #b66c83;
  font-weight: bold;
}

.tag {
  font-size: 10px;
  letter-spacing: 2px;
  color: #a27b68;
}

main {
  max-width: 720px;
  margin: auto;
  padding: 25px 18px 50px;
}

.hero {
  text-align: center;
  padding: 45px 15px;
  border-radius: 26px;
  background: linear-gradient(145deg, #fbe4eb, #fff5ed, #f7e9e8);
}

.eyebrow {
  font-size: 11px;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: #a15f75;
}

h1 {
  font-family: Georgia, serif;
  font-size: clamp(38px, 10vw, 58px);
  line-height: 1.1;
  font-weight: normal;
  margin: 20px 0;
}

h1 em {
  color: #b66c83;
}

p {
  line-height: 1.7;
}

.hero p {
  max-width: 420px;
  margin: 0 auto 25px;
  color: #725d62;
}

button {
  border: none;
  border-radius: 30px;
  padding: 14px 22px;
  font-size: 14px;
  cursor: pointer;
}

.primary {
  background: #b66c83;
  color: white;
}

.secondary {
  background: white;
  color: #9b5c70;
  border: 1px solid #ead2da;
}

section {
  margin-top: 35px;
}

.section-title {
  font-family: Georgia, serif;
  font-size: 30px;
  font-weight: normal;
  text-align: center;
}

.cards {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 13px;
}

.card {
  padding: 20px 15px;
  border-radius: 18px;
  background: white;
  border: 1px solid #f1e3e5;
}

.icon {
  font-size: 28px;
}

.card h3 {
  font-family: Georgia, serif;
  font-weight: normal;
  font-size: 19px;
  margin-bottom: 8px;
}

.card p {
  font-size: 13px;
  color: #79676a;
}

.panel {
  background: white;
  border: 1px solid #f0dfe4;
  border-radius: 22px;
  padding: 22px;
  margin-top: 18px;
}

.hidden {
  display: none;
}

.progress {
  height: 5px;
  background: #f4e7eb;
  border-radius: 10px;
  margin: 20px 0;
}

#progressBar {
  height: 5px;
  width: 0%;
  background: #b66c83;
  border-radius: 10px;
  transition: width .2s;
}

.answers {
  display: grid;
  gap: 10px;
  margin: 20px 0;
}

.answer {
  width: 100%;
  text-align: left;
  background: #fff8fa;
  border: 1px solid #f0dfe4;
  color: #45363a;
}

.answer.selected {
  border: 2px solid #b66c83;
  background: #fbe8ee;
}

footer {
  text-align: center;
  padding: 28px 15px;
  color: #947c82;
  font-size: 12px;
}

#result {
  text-align: center;
  line-height: 1.8;
}

@media (max-width: 380px) {
  .cards {
    grid-template-columns: 1fr;
  }
}
</style>
</head>

<body>

<header>
  <div>
    <div class="logo">Glow Up AI</div>
    <div class="tag">YOUR PERSONAL BEAUTY SPACE</div>
  </div>
  <div>♡</div>
</header>

<main>

  <div class="hero">
    <div class="eyebrow">Your beauty journey begins here</div>
    <h1>Your Glow-Up.<br><em>Your Rules.</em></h1>
    <p>
      Discover your personal beauty routine, find your style,
      and create a glow-up plan that fits your life and budget.
    </p>
    <button class="primary" onclick="startQuiz()">
      Start My Glow-Up ✨
    </button>
  </div>

  <section id="quiz" class="panel hidden">
    <div class="eyebrow">YOUR PERSONALIZED EXPERIENCE</div>
    <div class="progress">
      <div id="progressBar"></div>
    </div>
    <p id="step"></p>
    <h2 id="question" class="section-title"></h2>
    <div id="answers" class="answers"></div>
    <button class="primary" onclick="nextQuestion()" id="next">
      Continue →
    </button>
    <button class="secondary" onclick="skipQuestion()">
      Skip
    </button>
    <p id="message" aria-live="polite"></p>
  </section>

  <section id="features">
    <h2 class="section-title">Your Glow-Up, Your Way</h2>

    <div class="cards">
      <div class="card">
        <div class="icon">🌸</div>
        <h3>Skin & Beauty</h3>
        <p>Explore skincare routines and beauty tips suited to your preferences.</p>
      </div>

      <div class="card">
        <div class="icon">💄</div>
        <h3>Makeup Studio</h3>
        <p>Discover makeup inspiration, techniques, and products.</p>
      </div>

      <div class="card">
        <div class="icon">👗</div>
        <h3>AI Stylist</h3>
        <p>Explore outfit ideas that match your aesthetic and budget.</p>
      </div>

      <div class="card">
        <div class="icon">✨</div>
        <h3>My Glow-Up</h3>
        <p>Build routines and keep track of the habits you want to develop.</p>
      </div>
    </div>
  </section>

  <section id="personalPlan" class="panel hidden">
    <h2 class="section-title">Your Glow-Up Starter Plan</h2>
    <div id="result"></div>
    <button class="secondary" onclick="startQuiz()">Retake Quiz</button>
  </section>

</main>

<footer>
  GLOW UP AI · YOUR JOURNEY, YOUR WAY ♡
  <p>Your beauty journey is personal. Your choices are always yours.</p>
</footer>

<script>
const questions = [
  {
    title: "What do you want to focus on?",
    options: ["Skincare", "Makeup", "Haircare", "Fashion", "My complete glow-up"]
  },
  {
    title: "What is your main beauty goal?",
    options: ["A simple routine", "Healthy-looking skin", "Learn makeup", "Find my style", "Build better habits"]
  },
  {
    title: "How would you describe your skin?",
    options: ["Dry", "Oily", "Combination", "Normal", "Sensitive", "Not sure", "Skip"]
  },
  {
    title: "What's your budget per product?",
    options: ["Under $15", "$15–$30", "$31–$60", "$61+", "It depends"]
  },
  {
    title: "Which aesthetic do you love?",
    options: ["Clean girl", "Old money", "Coquette", "Y2K", "Casual chic", "Sporty", "Luxury glam", "Still discovering"]
  },
  {
    title: "How much time do you have daily?",
    options: ["5 minutes", "10 minutes", "15 minutes", "30 minutes or more"]
  }
];

let current = 0;
let selected = "";
let responses = [];

function startQuiz() {
  current = 0;
  responses = [];
  document.getElementById("quiz").classList.remove("hidden");
  document.getElementById("features").classList.add("hidden");
  document.getElementById("personalPlan").classList.add("hidden");
  renderQuestion();
  document.getElementById("quiz").scrollIntoView({behavior:"smooth"});
}

function renderQuestion() {
  selected = "";
  const q = questions[current];

  document.getElementById("step").textContent =
    "QUESTION " + (current + 1) + " OF " + questions.length;

  document.getElementById("question").textContent = q.title;

  document.getElementById("progressBar").style.width =
    (current / questions.length * 100) + "%";

  document.getElementById("message").textContent = "";

  const container = document.getElementById("answers");
  container.innerHTML = "";

  q.options.forEach(option => {
    const button = document.createElement("button");
    button.className = "answer";
    button.textContent = option;

    button.onclick = () => {
      selected = option;
      container.querySelectorAll("button").forEach(b => {
        b.classList.remove("selected");
      });
      button.classList.add("selected");
    };

    container.appendChild(button);
  });

  document.getElementById("next").textContent =
    current === questions.length - 1 ? "Create My Plan ✨" : "Continue →";
}

function nextQuestion() {
  if (!selected) {
    document.getElementById("message").textContent =
      "Choose an answer to continue, lovely! ♡";
    return;
  }

  responses[current] = selected;
  advance();
}

function skipQuestion() {
  responses[current] = "Not specified";
  advance();
}

function advance() {
  if (current < questions.length - 1) {
    current++;
    renderQuestion();
  } else {
    showPlan();
  }
}

function showPlan() {
  document.getElementById("quiz").classList.add("hidden");
  document.getElementById("personalPlan").classList.remove("hidden");

  const focus = responses[0] || "your glow-up";
  const goal = responses[1] || "your beauty goals";
  const budget = responses[3] || "your budget";
  const style = responses[4] || "your personal style";
  const time = responses[5] || "10 minutes";

  const result = document.getElementById("result");

  result.replaceChildren();

  const intro = document.createElement("p");
  intro.textContent = "Your focus is " + focus.toLowerCase() +
    ", with a goal of " + goal.toLowerCase() + ".";
  result.appendChild(intro);

  const details = [
    "Daily time: " + time,
    "Product budget: " + budget,
    "Preferred aesthetic: " + style,
    "Start with a manageable routine and adjust it to your needs.",
    "Review your preferences as your goals change."
  ];

  details.forEach(text => {
    const p = document.createElement("p");
    p.textContent = text;
    result.appendChild(p);
  });

  const note = document.createElement("p");
  note.textContent =
    "This is a basic starter plan generated in your browser, not an AI-powered recommendation. Your answers have not been saved to an account.";
  result.appendChild(note);

  document.getElementById("progressBar").style.width = "100%";
  document.getElementById("personalPlan").scrollIntoView({behavior:"smooth"});
}
</script>


</body>
</html>
