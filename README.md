<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    body {
      font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
      background: #f8f8f8;
      text-align: center;
      padding: 5rem 2rem;
    }
    h1 {
      color: #333;
      font-size: 1.8rem;
    }
    p {
      color: #666;
      font-size: 1rem;
    }
    a {
      display: inline-block;
      margin-top: 1.5rem;
      padding: 0.8rem 1.5rem;
      background: #3b82f6;
      color: white;
      text-decoration: none;
      border-radius: 8px;
      font-size: 1.1rem;
    }
    a:hover {
      background: #2563eb;
    }
    #fallback {
      display: none;
      margin-top: 2.5rem;
    }
  </style>
</head>
<body>
  <h1>🎉 活動頁面正在開啟中...</h1>
  <p>若未自動跳轉，請點下方按鈕</p>
  <a href="https://script.google.com/macros/s/AKfycbz83W8Ez0laszoAfNuO_vhYlWAHWMhVzj1cOWbjD0pWwHWVwvhsX_30jnCH7ODO99Gs/exec" target="_blank">
    👉 立即前往活動頁面
  </a>

  <div id="fallback">
    <h2>⚠️ 無法載入活動頁面</h2>
    <p>請改用無痕模式、手機熱點，或填寫下方表單由工作人員協助處理：</p>
    <a href="https://docs.google.com/forms/d/你的表單ID/viewform" target="_blank">
      📝 填寫備用表單
    </a>
  </div>

  <script>
    const rawUrl = "https://script.google.com/macros/s/AKfycbz83W8Ez0laszoAfNuO_vhYlWAHWMhVzj1cOWbjD0pWwHWVwvhsX_30jnCH7ODO99Gs/exec";
    if (/\/u\/\d+\//.test(window.location.href)) {
      location.replace(window.location.href.replace(/\/u\/\d+\//, '/'));
    }

    fetch(rawUrl, { method: 'GET', mode: 'no-cors' })
      .then(() => { location.href = rawUrl; })
      .catch(() => {
        document.getElementById("fallback").style.display = "block";
      });
  </script>
</body>
</html>
