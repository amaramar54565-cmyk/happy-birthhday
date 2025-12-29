# happy-birthhday
trial
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>🎂 Birthday Surprise 🎂</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Segoe UI', Arial, sans-serif;
      color: white;
      text-align: center;
    }

    .box {
      background: rgba(0,0,0,0.25);
      padding: 30px;
      border-radius: 20px;
      max-width: 360px;
      animation: fadeIn 2s ease;
    }

    h1 {
      animation: pulse 1.5s infinite alternate;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.9); }
      to { opacity: 1; transform: scale(1); }
    }

    @keyframes pulse {
      from { transform: scale(1); }
      to { transform: scale(1.06); }
    }

    #surprise {
      display: none;
    }
  </style>
</head>
<body>

  <!-- COUNTDOWN -->
  <div class="box" id="countdownBox">
    <h1>⏳ Countdown</h1>
    <p id="timer">Loading...</p>
    <p>Something special is waiting 💖</p>
  </div>

  <!-- SURPRISE -->
  <div class="box" id="surprise">
    <h1>🎉 Happy Birthday 🎉</h1>
    <p>
      I waited for this moment 💙<br><br>
      You mean more to me than you know 🥺
    </p>
    <p>
      Text me <b>“awww”</b> if you’re smiling 😌
    </p>
  </div>

  <script>
    // 👉 SET BIRTHDAY DATE & TIME HERE
    const birthday = new Date("2025-01-03T00:00:00").getTime();

    const timer = setInterval(() => {
      const now = new Date().getTime();
      const diff = birthday - now;

      if (diff <= 0) {
        clearInterval(timer);
        document.getElementById("countdownBox").style.display = "none";
        document.getElementById("surprise").style.display = "block";
        return;
      }

      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const minutes = Math.floor((diff / (1000 * 60)) % 60);
      const seconds = Math.floor((diff / 1000) % 60);

      document.getElementById("timer").innerHTML =
        `${days}d ${hours}h ${minutes}m ${seconds}s`;
    }, 1000);
  </script>

</body>
</html>
