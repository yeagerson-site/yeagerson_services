
<!-- ⬇️ START OF HTML FILE ⬇️ -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Yeagerson Services</title>
  <link href="https://fonts.googleapis.com/css2?family=Manrope:wght@400;700&display=swap" rel="stylesheet" />
  <style>
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: 'Manrope', sans-serif;
      color: #f2f2f2;
      background-color: #000;
      overflow-x: hidden;
    }
    canvas#stars {
      position: fixed;
      top: 0;
      left: 0;
      z-index: -1;
      width: 100vw;
      height: 100vh;
    }
    header {
      background: linear-gradient(135deg, #4A4E69, #6c5ce7);
      text-align: center;
      padding: 60px 20px 40px;
      color: white;
      position: relative;
      overflow: hidden;
    }
    .logo {
      font-size: 42px;
      font-weight: 700;
      position: relative;
      z-index: 1;
    }
    .subtext {
      font-size: 20px;
      opacity: 0.95;
      z-index: 1;
      position: relative;
    }
    .shine {
      content: '';
      position: absolute;
      top: 0;
      left: -75%;
      width: 50%;
      height: 100%;
      background: linear-gradient(120deg, transparent, rgba(255,255,255,0.3), transparent);
      transform: skewX(-25deg);
      animation: shine 3s infinite;
      z-index: 0;
    }
    @keyframes shine {
      0% { left: -75%; }
      100% { left: 125%; }
    }
    .loader {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background-color: #000;
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 9999;
    }
    .y-loader {
      width: 50px;
      height: 50px;
      border: 6px solid #fff;
      border-top: 6px solid #6c5ce7;
      border-radius: 50%;
      animation: spin 1s linear infinite;
    }
    @keyframes spin {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }
    .button, .action-btn {
      display: inline-block;
      background: linear-gradient(135deg, #00bcd4, #0097a7);
      color: white;
      padding: 12px 24px;
      margin: 10px;
      border: none;
      border-radius: 8px;
      font-weight: bold;
      text-decoration: none;
      transition: all 0.3s ease;
      cursor: pointer;
    }
    .button:hover, .action-btn:hover {
      background: linear-gradient(135deg, #0097a7, #00bcd4);
      transform: scale(1.05);
    }
    .sections-row {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      padding: 60px 20px;
      gap: 20px;
    }
    .section-box {
      background: rgba(255,255,255,0.03);
      border-radius: 12px;
      padding: 30px;
      width: 300px;
      text-align: center;
      box-shadow: 0 0 15px rgba(0, 188, 212, 0.15);
    }
    .section-box h2 {
      color: #00bcd4;
      margin-bottom: 20px;
    }
    .toggle-container {
      text-align: center;
      margin: 40px 0 20px;
    }
    .pricing-table, .job-form-section, .fitness-links {
      max-width: 1000px;
      margin: 20px auto;
      padding: 20px;
      background: rgba(255,255,255,0.02);
      display: none;
    }
    table {
      width: 100%;
      border-collapse: collapse;
      color: #eee;
    }
    th, td {
      padding: 14px 20px;
      border-bottom: 1px solid #444;
    }
    th {
      color: #00bcd4;
    }
    .popup {
      display: none;
      position: fixed;
      top: 30%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: #1a1a2e;
      color: white;
      padding: 20px;
      border-radius: 10px;
      z-index: 1000;
      box-shadow: 0 0 15px rgba(0,188,212,0.4);
      text-align: center;
    }
    .popup.active {
      display: block;
    }
    .popup img {
      margin-top: 15px;
      width: 150px;
    }
    .sticky-cta {
      position: fixed;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      gap: 12px;
      background: rgba(0,0,0,0.7);
      padding: 10px 16px;
      border-radius: 12px;
      z-index: 999;
    }
  </style>
</head>
<body>
  <canvas id="stars"></canvas>
  <div class="loader"><div class="y-loader"></div></div>
  <header>
    <div class="shine"></div>
    <div class="logo">YEAGERSON SERVICES</div>
    <p class="subtext">Design. Fitness. Digital Strategy — Professional. Tactical. Real.</p>
    <div class="buttons">
      <a href="mailto:adityacharak14@gmail.com" class="button">Email</a>
      <a href="tel:+919469264220" class="button">Call</a>
      <a href="https://instagram.com/son__yeager_" class="button" target="_blank">Instagram</a>
    </div>
  </header>

  <div class="sections-row">
    <div class="section-box">
      <h2>Courses</h2>
      <button class="action-btn" onclick="triggerConfetti(); showPopup('https://drive.google.com/file/d/14z-n1asG1wl_iUopF8T_bHSO3og7-UNr/view')">Buy ₹999</button>
    </div>
    <div class="section-box">
      <h2>Fitness Plans</h2>
      <button class="action-btn" onclick="toggleSection('fitnessLinks')">View Plans</button>
    </div>
  </div>

  <div class="toggle-container">
    <button class="action-btn" onclick="toggleSection('pricingTable')">View Price Chart</button>
    <button class="action-btn" onclick="toggleSection('jobFormSection')">Apply for a Role</button>
  </div>

  <section class="fitness-links" id="fitnessLinks">
    <h3>Fitness Plans</h3>
    <button class="button" onclick="showPopup('https://drive.google.com/file/d/1w-K6jdyIJDYzCm5nDDvTbyW2Zo2FS6CK/view?usp=drive_link')">Bulking Plan - ₹999</button>
    <button class="button" onclick="showPopup('https://drive.google.com/file/d/1_0z30spMx8Qg0nAA8qIwrF26a1n0sjbi/view?usp=drive_link')">Cutting Plan - ₹999</button>
  </section>

  <section class="pricing-table" id="pricingTable">
    <table>
      <tr><th>Service</th><th>Description</th><th>Price</th><th></th></tr>
      <tr><td>Full Website UI</td><td>3–5 page responsive design</td><td>₹4999</td><td><button class="action-btn" onclick="showPopup()">Buy</button></td></tr>
      <tr><td>Landing Page</td><td>Single-page HTML site</td><td>₹2499</td><td><button class="action-btn" onclick="showPopup()">Buy</button></td></tr>
    </table>
  </section>

  <section class="job-form-section" id="jobFormSection">
    <h2>💼 Join the Yeagerson Force</h2>
    <p>We're always looking for raw talent. Apply now:</p>
    <iframe src="https://docs.google.com/forms/d/e/1FAIpQLSeGxgOCqAzI-d8mpKss4QXefyI48pKEvjm5rFyBHxBMoZhDMw/viewform?embedded=true" width="100%" height="800" frameborder="0">Loading…</iframe>
  </section>

  <div class="popup" id="popup">
    <strong>Send payment to:</strong><br>
    <code>9469264220@ybl</code><br>
    <img src="https://api.qrserver.com/v1/create-qr-code/?data=upi://pay?pa=9469264220@ybl" alt="QR Code"><br>
    <small>Use your UPI app to complete the payment</small>
  </div>

  <div class="sticky-cta">
    <button class="action-btn" onclick="showPopup('https://drive.google.com/file/d/14z-n1asG1wl_iUopF8T_bHSO3og7-UNr/view')">Buy Now</button>
    <a href="#jobFormSection" class="action-btn">Apply</a>
    <a href="https://instagram.com/son__yeager_" class="action-btn" target="_blank">Insta</a>
  </div>

  <script>
    window.onload = () => {
      document.querySelector('.loader').style.display = 'none';
    };
    function showPopup(link) {
      const popup = document.getElementById('popup');
      popup.classList.add('active');
      setTimeout(() => {
        popup.classList.remove('active');
        if (link) window.open(link, '_blank');
      }, 4000);
    }
    function toggleSection(id) {
      const section = document.getElementById(id);
      section.style.display = (section.style.display === 'none' || section.style.display === '') ? 'block' : 'none';
      section.scrollIntoView({ behavior: "smooth" });
    }
    const canvas = document.getElementById('stars');
    const ctx = canvas.getContext('2d');
    const stars = [];
    function resizeCanvas() {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    }
    window.addEventListener('resize', resizeCanvas);
    resizeCanvas();
    for (let i = 0; i < 100; i++) {
      stars.push({
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height,
        r: Math.random() * 1.5,
        d: Math.random() * 1
      });
    }
    function drawStars() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      ctx.fillStyle = "white";
      ctx.shadowBlur = 2;
      ctx.shadowColor = "white";
      for (let i = 0; i < stars.length; i++) {
        const s = stars[i];
        ctx.beginPath();
        ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2, true);
        ctx.fill();
        s.y += s.d;
        if (s.y > canvas.height) {
          s.y = 0;
          s.x = Math.random() * canvas.width;
        }
      }
    }
    setInterval(drawStars, 33);
    function triggerConfetti() {
      // Optional: add confetti effect later
    }
  </script>
</body>
</html>
<!-- ⬆️ END OF FILE ⬆️ -->
