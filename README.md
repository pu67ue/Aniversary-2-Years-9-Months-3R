<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>สุขสันต์วันครบรอบ</title>
  <style>
    /* กำหนดตัวแปรสีไล่โทนจากชมพูไปเขียวอ่อน */
    :root {
      --pink-start: #FCE8E6;      /* สีชมพูพาสเทลนุ่มนวล */
      --green-end: #E4EBE2;       /* สีเขียวอ่อนพาสเทล (อิงตาม Dingley) */
      --card-bg: #FFFFFF;         /* สีพื้นหลังการ์ดขาวสะอาด */
      --primary-text: #6A784D;    /* สีเขียวเข้ม (Kombu Green) สำหรับข้อความ */
      --secondary-text: #C08267;  /* สีส้มอิฐ/ชมพูเข้ม (Pale Copper) */
      --border-color: #3A3D32;    /* เส้นขอบการ์ดบางๆ */
      --btn-bg: #5C7859;          /* สีปุ่มกด (Dingley) */
      --btn-hover: #354231;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    /* จัดทุกอย่างให้อยู่ตรงกลางหน้าจอแบบสมบูรณ์ + พื้นหลังไล่สี */
    body {
          body {
      /* เพิ่ม SVG รูปหัวใจลางๆ ซ้อนบนพื้นหลังไล่สีเดิม */
      background: 
        url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='60' height='60' viewBox='0 0 24 24' fill='%23C08267' opacity='0.45'%3E%3Cpath d='M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z'/%3E%3C/svg%3E") repeat,
        linear-gradient(135deg, var(--pink-start) 0%, var(--green-end) 100%);
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
      max-width: 420px;
      padding: 50px 30px;
      border-radius: 24px;
      border: 1px solid var(--border-color);
      box-shadow: 0 15px 35px rgba(0, 0, 0, 0.05);
      
      /* จัดเนื้อหาภายในให้อยู่ตรงกลางทั้งหมด */
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
    }

    /* หน้าจอแต่ละหน้า */
    .screen {
      width: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    /* ข้อความหัวข้อ */
    .title {
      font-size: 26px;
      font-weight: 700;
      color: var(--primary-text);
      line-height: 1.4;
    }

    .subtitle {
      font-size: 22px;
      color: var(--secondary-text);
      font-weight: 600;
      margin-top: 12px;
    }

    /* ช่องกรอกรหัสผ่าน */
    .input-group {
      margin: 30px 0;
      width: 100%;
      display: flex;
      justify-content: center;
    }

    .passcode-input {
      width: 100%;
      max-width: 200px;
      padding: 12px;
      text-align: center;
      font-size: 24px;
      letter-spacing: 8px;
      border: 1.5px solid var(--border-color);
      border-radius: 12px;
      outline: none;
      background-color: #FAFAFA;
      color: var(--primary-text);
      transition: all 0.2s;
    }

    .passcode-input:focus {
      border-color: var(--btn-bg);
      background-color: #FFFFFF;
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
      box-shadow: 0 4px 12px rgba(92, 120, 89, 0.25);
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
    <div id="passcode-screen" class="screen">
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
    <div id="flower-screen" class="screen content-screen">
      <div class="title">สุขสันต์วันครบรอบนะ เรน</div>
      <div class="subtitle">รักมากๆ นะ</div>
      <div class="subtitle">รักเรนที่สุดในโลกเลย ขอบคุณสำหรับทุกอย่างเลยนะเรน มิวรักเรน</div>
      <div class="subtitle">ณัฐธยาน์ ♥️ ณัฐกรณ์</div>
    </div>
  </div>

  <script>
    function checkPasscode() {
      const input = document.getElementById('passcode').value;
      // รหัสผ่านปลดล็อก
      const correctPasscode = "140224"; 

      if (input === correctPasscode) {
        document.getElementById('passcode-screen').style.display = 'none';
        document.getElementById('flower-screen').style.display = 'flex';
      } else {
        alert("รหัสผ่านไม่ถูกต้อง ลองใหม่อีกครั้งนะ ♡");
      }
    }
  </script>

</body>
</html>