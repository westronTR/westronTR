
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Instagram Şifre Kırıcı | By Westron</title>
  <style>
    * {
      margin: 0; padding: 0; box-sizing: border-box;
      font-family: 'Poppins', 'Segoe UI', sans-serif;
    }
    
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');
    
    body {
      background: linear-gradient(135deg, #0a0a0a 0%, #121212 100%);
      color: #00ff88;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      flex-direction: column;
      position: relative;
    }
    
    .logo {
      font-size: 28px;
      font-weight: 700;
      letter-spacing: 1px;
      margin-bottom: 20px;
      text-shadow: 0 0 10px #00ff88;
      text-transform: uppercase;
      position: relative;
    }
    
    .logo::before {
      content: 'By Westron';
      position: absolute;
      top: -25px;
      left: 50%;
      transform: translateX(-50%);
      font-size: 14px;
      letter-spacing: 3px;
      background: linear-gradient(to right, #ff0066, #00ff88, #0066ff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      animation: rainbow 3s linear infinite;
    }
    
    @keyframes rainbow {
      0% { filter: hue-rotate(0deg); }
      100% { filter: hue-rotate(360deg); }
    }
    
    .box {
      background: rgba(17, 17, 17, 0.9);
      padding: 40px 30px;
      border: 2px solid #00ff88;
      border-radius: 20px;
      box-shadow: 0 0 30px rgba(0, 255, 136, 0.3), inset 0 0 20px rgba(0, 255, 136, 0.1);
      width: 95%;
      max-width: 450px;
      text-align: center;
      margin: 10px;
      backdrop-filter: blur(10px);
      transition: all 0.3s ease;
      opacity: 0;
      transform: translateY(20px);
      animation: fadeIn 0.5s forwards;
    }
    
    @keyframes fadeIn {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    
    .box h2 {
      margin-bottom: 25px;
      font-size: 24px;
      font-weight: 600;
      text-shadow: 0 0 5px #00ff88;
    }
    
    input {
      width: 100%;
      padding: 15px;
      margin: 15px 0;
      background: rgba(0, 0, 0, 0.5);
      border: 1px solid #00ff88;
      color: #00ff88;
      border-radius: 8px;
      font-size: 16px;
      transition: all 0.3s ease;
      box-shadow: 0 0 8px rgba(0, 255, 136, 0.2);
    }
    
    input:focus {
      box-shadow: 0 0 15px rgba(0, 255, 136, 0.4);
      outline: none;
      background: rgba(0, 0, 0, 0.7);
    }
    
    input::placeholder {
      color: rgba(0, 255, 136, 0.5);
    }
    
    button {
      padding: 12px 25px;
      width: 80%;
      background: linear-gradient(45deg, #00cc66, #00ff88);
      border: none;
      color: #000;
      font-weight: 600;
      font-size: 16px;
      border-radius: 8px;
      cursor: pointer;
      margin-top: 20px;
      transition: all 0.3s ease;
      text-transform: uppercase;
      letter-spacing: 1px;
      box-shadow: 0 5px 15px rgba(0, 255, 136, 0.3);
    }
    
    button:hover {
      transform: translateY(-3px);
      box-shadow: 0 8px 20px rgba(0, 255, 136, 0.5);
      background: linear-gradient(45deg, #00ff88, #00cc66);
    }
    
    button:active {
      transform: translateY(0);
    }
    
    #loading {
      margin-top: 30px;
      font-size: 18px;
    }
    
    .hidden {
      display: none !important;
    }
    
    .avatar {
      width: 120px;
      height: 120px;
      border-radius: 50%;
      object-fit: cover;
      margin: 0 auto 25px;
      border: 3px solid #00ff88;
      box-shadow: 0 0 20px rgba(0, 255, 136, 0.5);
      transition: all 0.3s ease;
    }
    
    .back-btn {
      margin-top: 25px;
      color: #00ff88;
      text-decoration: none;
      cursor: pointer;
      display: inline-block;
      padding: 8px 15px;
      border: 1px solid rgba(0, 255, 136, 0.3);
      border-radius: 50px;
      font-size: 14px;
      transition: all 0.3s ease;
    }
    
    .back-btn:hover {
      background: rgba(0, 255, 136, 0.1);
      box-shadow: 0 0 10px rgba(0, 255, 136, 0.2);
    }
    
    #resultPassword {
      background: rgba(0, 0, 0, 0.5);
      padding: 20px;
      border-radius: 8px;
      margin: 20px 0;
      font-size: 18px;
      border: 1px dashed #00ff88;
      font-weight: 500;
      color: #fff;
      text-shadow: 0 0 5px #00ff88;
    }
    
    .loading-bar {
      height: 6px;
      width: 100%;
      background: rgba(0, 255, 136, 0.1);
      border-radius: 10px;
      margin: 20px 0;
      overflow: hidden;
      position: relative;
    }
    
    .loading-progress {
      position: absolute;
      height: 100%;
      width: 0%;
      background: linear-gradient(to right, #00cc66, #00ff88);
      border-radius: 10px;
      transition: width 0.5s ease;
    }
    
    .status-icon {
      display: inline-block;
      width: 10px;
      height: 10px;
      border-radius: 50%;
      margin-right: 10px;
      background: #00ff88;
      box-shadow: 0 0 10px #00ff88;
      animation: pulse 1.5s infinite;
    }
    
    @keyframes pulse {
      0% { transform: scale(1); opacity: 1; }
      50% { transform: scale(1.2); opacity: 0.7; }
      100% { transform: scale(1); opacity: 1; }
    }
    
    .footer {
      position: absolute;
      bottom: 20px;
      text-align: center;
      width: 100%;
      font-size: 12px;
      color: rgba(0, 255, 136, 0.7);
      padding: 10px;
    }
    
    .password-details {
      margin-top: 25px;
      text-align: left;
      font-size: 14px;
    }
    
    .detail-item {
      display: flex;
      justify-content: space-between;
      margin-bottom: 8px;
      padding-bottom: 8px;
      border-bottom: 1px dashed rgba(0, 255, 136, 0.2);
    }
    
    .detail-value {
      font-weight: 600;
      color: #fff;
    }
  </style>
</head>
<body>

<div class="logo">Instagram Şifre Kırıcı</div>

<div class="box" id="keyScreen">
  <h2>Giriş Anahtarı</h2>
  <input type="text" id="keyInput" placeholder="Erişim anahtarını gir..." autocomplete="off">
  <button onclick="checkKey()">GİRİŞ YAP</button>
</div>

<div class="box hidden" id="usernameScreen">
  <h2>Hedef Hesap</h2>
  <img src="https://resmim.net/cdn/2025/05/18/TSqFuc.webp" alt="Profile" class="avatar">
  <input type="text" id="usernameInput" placeholder="Instagram kullanıcı adını gir..." autocomplete="off">
  <button onclick="startHack()">ŞİFREYİ BUL</button>
  <div class="back-btn" onclick="goBackToKey()">← ANA SAYFA</div>
</div>

<div class="box hidden" id="loadingScreen">
  <h2>İşlem Devam Ediyor</h2>
  <div class="loading-bar">
    <div class="loading-progress" id="progressBar"></div>
  </div>
  <div id="loading"><span class="status-icon"></span>Proxy oluşturuluyor...</div>
  <div class="back-btn" onclick="goBackToUser()">İPTAL ET</div>
</div>

<div class="box hidden" id="resultScreen">
  <h2>Şifre Bulundu!</h2>
  <p id="resultPassword"></p>
  
  <div class="password-details">
    <div class="detail-item">
      <span>Algoritma:</span>
      <span class="detail-value">AES-256 + Rainbow Tables</span>
    </div>
    <div class="detail-item">
      <span>Güvenlik:</span>
      <span class="detail-value">Orta Seviye</span>
    </div>
    <div class="detail-item">
      <span>Sunucu:</span>
      <span class="detail-value">Instagram API v12.2</span>
    </div>
    <div class="detail-item">
      <span>IP Maskeleme:</span>
      <span class="detail-value">Aktif (17 Proxy)</span>
    </div>
  </div>
  
  <button onclick="startHack()">YENİ TARAMA</button>
  <div class="back-btn" onclick="goBackToUser()">GERİ DÖN</div>
</div>

<div class="footer">
  © 2025 WESTRON SECURITY | Tüm Hakları Saklıdır | v3.1.5
</div>

<script>
  const keyScreen = document.getElementById("keyScreen");
  const usernameScreen = document.getElementById("usernameScreen");
  const loadingScreen = document.getElementById("loadingScreen");
  const resultScreen = document.getElementById("resultScreen");
  const loading = document.getElementById("loading");
  const progressBar = document.getElementById("progressBar");
  
  // Animations
  document.addEventListener("DOMContentLoaded", function() {
    setTimeout(() => {
      keyScreen.style.opacity = "1";
      keyScreen.style.transform = "translateY(0)";
    }, 100);
  });

  function checkKey() {
    const key = document.getElementById("keyInput").value.trim();
    if (key === "@WESTR0N") {
      keyScreen.classList.add("hidden");
      usernameScreen.classList.remove("hidden");
    } else {
      alert("Erişim reddedildi! Doğru anahtarı girmelisiniz.");
    }
  }

  function startHack() {
    const username = document.getElementById("usernameInput").value.trim();
    if (!username) {
      alert("Lütfen geçerli bir kullanıcı adı giriniz!");
      return;
    }

    usernameScreen.classList.add("hidden");
    resultScreen.classList.add("hidden");
    loadingScreen.classList.remove("hidden");
    
    // Reset progress
    progressBar.style.width = "0%";

    // Progress steps
    const steps = [
      "Ağ taraması başlatıldı...",
      "Proxy sunucuları yapılandırılıyor...",
      "Instagram API'ye erişim sağlanıyor...",
      "Güvenlik duvarı aşılıyor...",
      "Şifre algoritması çözümleniyor...",
      "Veri tabanı karşılaştırması yapılıyor...",
      "Şifre bulundu! Doğrulanıyor..."
    ];
    
    let currentStep = 0;
    const interval = setInterval(() => {
      if (currentStep < steps.length) {
        loading.innerHTML = `<span class="status-icon"></span>${steps[currentStep]}`;
        progressBar.style.width = `${(currentStep + 1) * (100 / steps.length)}%`;
        currentStep++;
      } else {
        clearInterval(interval);
        
        loadingScreen.classList.add("hidden");
        resultScreen.classList.remove("hidden");

        // Generate password with better algorithm
        let password = generatePassword(username);
        document.getElementById("resultPassword").innerText = `@${username} için şifre: ${password}`;
      }
    }, 1200);
  }
  
  function generatePassword(username) {
    // More sophisticated password generation
    const commonWords = ["123", "official", "pass", "321", "instagram", "benim", "hesap"];
    const symbols = [".", "_", "!", ""];
    const numbers = ["123", "1905", "1907", "2023", "2025", "06", "34", "35", ""];
    
    let password = "";
    
    // 50% chance to use username as base
    if (Math.random() > 0.5) {
      password = username;
    } else {
      // Use common Turkish names if not using username
      const names = ["can", "mert", "ayse", "fatma", "mehmet", "ali", "veli"];
      password = names[Math.floor(Math.random() * names.length)];
    }
    
    // Add symbol
    password += symbols[Math.floor(Math.random() * symbols.length)];
    
    // Add common word or number
    if (Math.random() > 0.5) {
      password += commonWords[Math.floor(Math.random() * commonWords.length)];
    } else {
      password += numbers[Math.floor(Math.random() * numbers.length)];
    }
    
    return password;
  }

  function goBackToKey() {
    resultScreen.classList.add("hidden");
    usernameScreen.classList.add("hidden");
    loadingScreen.classList.add("hidden");
    keyScreen.classList.remove("hidden");
  }

  function goBackToUser() {
    loadingScreen.classList.add("hidden");
    resultScreen.classList.add("hidden");
    usernameScreen.classList.remove("hidden");
  }
  
  // Easter egg
  let clickCount = 0;
  document.querySelector('.logo').addEventListener('click', function() {
    clickCount++;
    if (clickCount >= 5) {
      alert('WESTRON Advanced Security Module v3.1.5');
      clickCount = 0;
    }
  });
  
  // Handle Enter key
  document.getElementById('keyInput').addEventListener('keypress', function(e) {
    if (e.key === 'Enter') {
      checkKey();
    }
  });
  
  document.getElementById('usernameInput').addEventListener('keypress', function(e) {
    if (e.key === 'Enter') {
      startHack();
    }
  });
</script>

</body>
</html>
