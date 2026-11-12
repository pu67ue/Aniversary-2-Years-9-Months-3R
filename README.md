<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>สุขสันต์วันครบรอบ</title>
  <style>
    /* กำหนดตัวแปรสีให้สว่าง อ่อนหวาน และละมุนยิ่งขึ้น */
    :root {
      --bg-body: #F4EFEA;         /* สีพื้นหลังภายนอกอ่อนๆ */
      --card-bg: #FCF9F5;         /* สีพื้นหลังการ์ดโทนสว่างนุ่มนวล */
      --primary-text: #4A5D4E;    /* สีเขียวเข้มสบายตา */
      --secondary-text: #C47B5E;  /* สีส้มอิฐพาสเทลอ่อน */
      --border-color: #E6D8C8;    /* สีเส้นขอบครีมอ่อน */
      --btn-bg: #78937A;          /* สีปุ่มกด */
      --btn-hover: #5A735C;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background-color: var(--bg-body);
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      padding: 20px;
    }

    /* การ์ดความรักตรงกลาง */
    .card {
      background: var(--card-bg);
      width: 100%;
      max-width: 450px;
      padding: 50px 30px;
      border-radius: 24px;
      border: 1px solid var(--border-color);
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.04);
      text-align: center;
    }

    /* ข้อความหัวข้อ */
    .title {
      font-size: 26px;
      font-weight: 700;
      color: var(--primary-text);
      margin-bottom: 20px;
      line-height: 1.4;
    }

    .subtitle {
      font-size: 22px;
      color: var(--secondary-text);
      font-weight: 600;
      margin-top: 10px;
    }

    /* ช่องกรอกรหัสผ่าน */
    .input-group {
      margin: 30px 0;
    }

    .passcode-input {
      width: 100%;
      max-width: 220px;
      padding: 12px;
      text-align: center;
      font-size: 24px;
      letter-spacing: 8px;
      border: 1.5px solid var(--border-color);
      border-radius: 12px;
      outline: none;
      background-color: #ffffff;
      color: var(--primary-text);
      transition: border-color 0.2s;
    }

    .passcode-input:focus {
      border-color: var(--btn-bg);
    }

    /* ปุ่มกด */
    .unlock-btn {
      background-color: var(--btn-bg);
      color: #ffffff;
      border: none;
      padding: 12px 35px;
      font-size: 15px;
      font-weight: 600;
      letter-spacing: 1px;
      border-radius: 20px;
      cursor: pointer;
      box-shadow: 0 4px 12px rgba(120, 147, 122, 0.25);
      transition: all 0.2s ease;
    }

    .unlock-btn:hover {
      background-color: var(--btn-hover);
      transform: translateY(-1px);
    }

    .unlock-btn:active {
      transform: scale(0.98);
    }

    /* ส่วนแสดงผลหลังใส่รหัสผ่านถูก (หน้าสอง) */
    .content-screen {
      display: none;
      animation: fadeIn 0.8s ease-in-out;
      padding: 20px 0;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(8px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>

  <div class="card">
    <!-- 1. หน้ากรอกรหัสผ่าน -->
    <div id="passcode-screen">
      <div class="title">สุขสันต์วันครบรอบ</div>
      <div class="input-group">
        <input 
          type="password" 
          id="passcode" 
          class="passcode-input" 
          placeholder="••••••" 
          maxlength="6" 
        />
      </div>
      <button class="unlock-btn" onclick="checkPasscode()">ปลดล็อก ♡</button>
    </div>

    <!-- 2. หน้าแสดงผลหลังกรอกรหัสผ่านถูกต้อง (140224) -->
    <div id="flower-screen" class="content-screen">
      <div class="title">สุขสันต์วันครบรอบนะ เรน</div>
      <div class="subtitle">รักมากๆ นะ</div>
    </div>
  </div>

  <script>
    function checkPasscode() {
      const input = document.getElementById('passcode').value;
      // รหัสผ่านปลดล็อก
      const correctPasscode = "140224"; 

      if (input === correctPasscode) {
        document.getElementById('passcode-screen').style.display = 'none';
        document.getElementById('flower-screen').style.display = 'block';
      } else {
        alert("รหัสผ่านไม่ถูกต้อง ลองใหม่อีกครั้งนะ ♡");
      }
    }
  </script>

</body>
</html># Aniversary-2-Years-9-Months-3R