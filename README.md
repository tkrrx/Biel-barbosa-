<Barbearia> <\TA MUITO MARRENTA<
<div class="center-text">
    
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Quiz Interativo</title>
  <style>
    body { font-family: Arial, sans-serif; background: #111; color: #fff; padding: 20px; }
    .quiz-container { max-width: 600px; margin: auto; }
    h1 { text-align: center; }
    .question { margin-bottom: 20px; }
    button { display: block; margin-top: 10px; padding: 10px; width: 100%; border: none; background: #333; color: white; border-radius: 5px; }
    button:hover { background: #555; }
    #result { margin-top: 20px; font-size: 18px; text-align: center; }
  </style>
</head>
<body>
  <div class="quiz-container">
    <h1>Quiz Rápido 🧠</h1>
    <div id="quiz"></div>
    <div id="result"></div>
  </div>

  <script>
    const questions = [
      {
        question: "Qual é a capital do Brasil?",
        options: ["São Paulo", "Brasília", "Rio de Janeiro"],
        answer: "Brasília"
      },
      {
        question: "Quem criou o sistema Android?",
        options: ["Google", "Apple", "Microsoft"],
        answer: "Google"
      },
      {
        question: "Qual desses é um estilo musical?",
        options: ["Funk", "Python", "Chrome"],
        answer: "Funk"
      }
    ];

    let current = 0;
    let score = 0;

    function loadQuestion() {
      if (current >= questions.length) {
        document.getElementById("quiz").innerHTML = "";
        document.getElementById("result").innerText = `Você acertou ${score} de ${questions.length} perguntas!`;
        return;
      }

      const q = questions[current];
      let html = `<div class="question"><h2>${q.question}</h2>`;
      q.options.forEach(opt => {
        html += `<button onclick="checkAnswer('${opt}')">${opt}</button>`;
      });
      html += `</div>`;
      document.getElementById("quiz").innerHTML = html;
    }

    function checkAnswer(selected) {
      if (selected === questions[current].answer) {
        score++;
      }
      current++;
      loadQuestion();
    }

    loadQuestion();
  </script>
</body>
</html>
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>🎰 Mini Slot Machine</title>
  <style>
    body {
      background: #111;
      color: white;
      font-family: 'Arial', sans-serif;
      text-align: center;
      padding-top: 50px;
    }
    h1 {
      margin-bottom: 30px;
    }
    #slot {
      font-size: 50px;
      margin: 20px auto;
      letter-spacing: 30px;
    }
    button {
      padding: 15px 30px;
      font-size: 20px;
      background: gold;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      margin-top: 20px;
    }
    #result {
      font-size: 24px;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>🎰 Slot Machine</h1>
  <div id="slot">🍒🍋🍊</div>
  <button onclick="play()">GIRAR</button>
  <div id="result"></div>

  <script>
    const symbols = ["🍒", "🍋", "🍊", "🍉", "🔔", "⭐", "💎"];

    function play() {
      const slot = document.getElementById("slot");
      const result = document.getElementById("result");

      // Gera 3 símbolos aleatórios
      let a = symbols[Math.floor(Math.random() * symbols.length)];
      let b = symbols[Math.floor(Math.random() * symbols.length)];
      let c = symbols[Math.floor(Math.random() * symbols.length)];

      slot.innerText = `${a}${b}${c}`;

      // Verifica o resultado
      if (a === b && b === c) {
        result.innerText = "🎉 JACKPOT! Você ganhou!";
      } else if (a === b || b === c || a === c) {
        result.innerText = "👏 Quase lá! Duas iguais.";
      } else {
        result.innerText = "😢 Tente de novo!";
      }
    }
  </script>
</body>
</html>
