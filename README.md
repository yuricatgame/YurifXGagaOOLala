//<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>正在前往活動頁面...</title>
  <style>
    body {
      font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
      background: #f8f8f8;
      text-align: center;
      padding: 5rem 2rem;
    }
    h1 {
      color: #333;
      font-size: 2rem;
    }
    a {
      display: inline-block;
      margin-top: 1.5rem;
      padding: 0.8rem 1.5rem;
      background: #0078D4;
      color: white;
      text-decoration: none;
      border-radius: 8px;
      font-size: 1.2rem;
    }
    a:hover {
      background: #005fa3;
    }
    #fallback {
      display: none;
      margin-top: 2rem;
    }
  </style>
</head>
<body>
  <h1>🎉 活動頁面正在開啟中...</h1>
  <p>若未自動跳轉，請點下方按鈕</p>
  <a id="manual-link" href="https://script.google.com/macros/s/AKfycbz83W8Ez0laszoAfNuO_vhYlWAHWMhVzj1cOWbjD0pWwHWVwvhsX_30jnCH7ODO99Gs/exec" target="_blank" rel="noopener noreferrer">
    👉 立即前往活動頁面
  </a>

  <div id="fallback">
    <h2>⚠️ 無法載入活動頁面</h2>
    <p>可能是因為公司網路、Google 帳號權限或其他瀏覽器設定所致。</p>
    <p>請改用手機熱點、無痕模式，或填寫以下備用表單由工作人員協助處理：</p>
    <a href="https://docs.google.com/forms/d/你的表單ID/viewform" target="_blank" rel="noopener noreferrer">
      📝 填寫備用表單
    </a>
  </div>

  <script>
    // 🔧 原始網址（正確無 /u/X 的版本）
    const rawUrl = "https://script.google.com/macros/s/AKfycbz83W8Ez0laszoAfNuO_vhYlWAHWMhVzj1cOWbjD0pWwHWVwvhsX_30jnCH7ODO99Gs/exec";

    // 若有人從錯誤網址開進來（含 /u/1），這裡會導正他
    const currentUrl = window.location.href;
    if (/\/u\/\d+\//.test(currentUrl)) {
      const cleanedUrl = currentUrl.replace(/\/u\/\d+\//, '/');
      window.location.replace(cleanedUrl); // 🔄 用乾淨網址重新整理
    }

    // 正常流程：fetch 檢查是否可連線
    fetch(rawUrl)
      .then(res => res.text())
      .then(text => {
        if (text.includes("<html") || text.includes("DOCTYPE")) {
          window.location.href = rawUrl;
        } else {
          showFallback();
        }
      })
      .catch(() => {
        showFallback();
      });

    function showFallback() {
      document.getElementById("fallback").style.display = "block";
    }
  </script>
</body>
</html>
