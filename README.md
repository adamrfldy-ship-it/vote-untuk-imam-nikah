<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Polling Jodoh Imam Guswali</title><img src="imam.jpg" alt="Imam Guswali">
  

  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #e8f5e9, #f1f8e9);
      text-align: center;
      padding: 30px;
      color: #333;
    }

    h1 {
      color: #2e7d32;
    }

    .card {
      background: white;
      max-width: 500px;
      margin: auto;
      padding: 25px;
      border-radius: 15px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }

    button {
      width: 100%;
      padding: 12px;
      margin: 8px 0;
      font-size: 16px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      background-color: #66bb6a;
      color: white;
      font-weight: bold;
    }

    button:hover {
      background-color: #43a047;
    }

    .result {
      margin-top: 15px;
      font-size: 15px;
    }

    footer {
      margin-top: 25px;
      font-size: 13px;
      color: #555;
    }
  </style>
</head>

<body>

  <h1>📊 Polling Jodoh Nasional</h1>

  <div class="card">
    <h2>Menurut Anda...</h2>
    <p><strong>Apakah Imam Guswali sudah waktunya menikah? 😭🤣</strong></p>

    <button onclick="vote(0)">😇 Sudah banget, kasihan</button>
    <button onclick="vote(1)">🤔 Sudah, tapi nunggu calon</button>
    <button onclick="vote(2)">😂 Belum, masih fokus healing</button>
    <button onclick="vote(3)">🫣 Jangan ditanya dulu</button>

    <div class="result" id="result"></div>
  </div>

  <footer>
    *Polling ini 100% bercanda. Imam harap bersabar 🙏😂
  </footer>

  <script>
    let votes = [0, 0, 0, 0];

    function vote(index) {
      votes[index]++;
      showResult();
    }

    function showResult() {
      let total = votes.reduce((a, b) => a + b, 0);
      let labels = [
        "😇 Sudah banget, kasihan",
        "🤔 Sudah, tapi nunggu calon",
        "😂 Masih healing",
        "🫣 Jangan ditanya dulu"
      ];

      let html = "<h3>Hasil Sementara:</h3>";
      for (let i = 0; i < votes.length; i++) {
        let percent = total ? ((votes[i] / total) * 100).toFixed(1) : 0;
        html += `<p>${labels[i]}: <strong>${percent}%</strong></p>`;
      }

      document.getElementById("result").innerHTML = html;
    }
  </script>

</body>
</html>
