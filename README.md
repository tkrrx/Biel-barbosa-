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