<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bà có đang ghét tui không?</title>
  <style>
    body {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #ffe4ec;
      font-family: Arial, sans-serif;
      text-align: center;
      overflow: hidden;
    }
    h1 {
      font-size: 2rem;
      color: #333;
      margin-bottom: 40px;
      z-index: 10;
    }
    button {
      padding: 12px 24px;
      font-size: 18px;
      border: none;
      border-radius: 8px;
      background-color: #ff7aa2;
      color: white;
      cursor: pointer;
      transition: background-color 0.3s;
      position: absolute;
    }
    button:hover {
      background-color: #ff4e88;
    }
    #noBtn { }
    #yesBtn {
      bottom: 100px;
      position: relative;
    }
    .heart {
      position: fixed;
      top: -20px;
      font-size: 24px;
      color: #ff4e88;
      animation: fall 4s linear infinite;
    }
    @keyframes fall {
      0% { transform: translateY(0) rotate(0deg); opacity: 1; }
      100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
    }
  </style>
</head>
<body>
  <h1>Bà có đang ghét tui không?</h1>
  <button id="noBtn">Không</button>
  <button id="yesBtn" onclick="alert('À bà ghét tui huhu 😭')">Có</button>

  <script>
    // tạo tim rơi
    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.innerHTML = "💖";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = (2 + Math.random() * 3) + "s";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 5000);
    }
    setInterval(createHeart, 500);

    // nút Không chạy trốn
    const noBtn = document.getElementById("noBtn");
    noBtn.addEventListener("mouseover", () => {
      const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
      const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
      noBtn.style.left = `${x}px`;
      noBtn.style.top = `${y}px`;
    });
  </script>
</body>
</html>
