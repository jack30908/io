<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8">
  <title>可愛抽抽樂</title>
  <style>
    body {
      font-family: "Noto Sans TC", sans-serif;
      background-color: #fffafc;
      text-align: center;
      padding: 2rem;
      color: #ff66a3;
    }
    h1 {
      font-size: 2.5rem;
      margin-bottom: 1rem;
    }
    .prize-list {
      font-size: 1.1rem;
      margin-bottom: 2rem;
      color: #ff1493;
    }
    button {
      padding: 1rem 2rem;
      font-size: 1.5rem;
      background-color: #ffd1dc;
      border: none;
      border-radius: 15px;
      cursor: pointer;
      box-shadow: 2px 2px 10px rgba(255, 105, 180, 0.3);
      transition: transform 0.2s ease;
    }
    button:hover {
      transform: scale(1.05);
    }
    .result {
      font-size: 2rem;
      margin-top: 2rem;
      color: #d63384;
    }
  </style>
</head>
<body>
  <h1>🎁 歡迎來到可愛抽抽樂 🎁</h1>
  <div class="prize-list">
    獎項包括：抽抽樂 × 35、點心 × 5、盒玩 × 5、飲料 × 5<br>
    每個獎項抽出後會從獎池中移除喔！
  </div>
  <button onclick="drawPrize()">點我抽獎！</button>
  <div class="result" id="result"></div>

  <script>
    let prizePool = [
      ...Array(35).fill('抽抽樂'),
      ...Array(5).fill('點心'),
      ...Array(5).fill('盒玩'),
      ...Array(5).fill('飲料')
    ];

    function drawPrize() {
      if (prizePool.length === 0) {
        document.getElementById('result').textContent = '所有獎項都抽完囉！';
        return;
      }
      const index = Math.floor(Math.random() * prizePool.length);
      const prize = prizePool.splice(index, 1)[0];
      document.getElementById('result').textContent = `🎉 你抽中了：${prize}！`;
    }
  </script>
</body>
</html>
