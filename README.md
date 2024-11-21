<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mở khóa đoạn ghi âm</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      text-align: center;
      margin: 0;
      background-image: url('https://images.unsplash.com/photo-1572947650446-d9e0c0b65d7c?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&q=80&w=1080'); /* Hình nền ngọn đồi hoa */
      background-size: cover;
      background-attachment: fixed;
      background-position: center;
      color: white;
    }

    .container {
      max-width: 400px;
      margin: auto;
      padding: 20px;
      background-color: rgba(255, 192, 203, 0.8); /* Màu hồng nhạt */
      border-radius: 15px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
      margin-top: 50px;
    }

    h2 {
      font-family: 'Cursive', sans-serif;
      font-size: 1.8em;
      color: #d32f2f;
      margin-bottom: 20px;
    }

    input[type="password"] {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 2px solid #d81b60;
      border-radius: 5px;
      font-size: 1em;
    }

    button {
      padding: 10px 20px;
      border: none;
      background-color: #d81b60;
      color: white;
      border-radius: 5px;
      font-size: 1.1em;
      cursor: pointer;
    }

    button:hover {
      background-color: #ad1457;
    }

    .audio-container {
      display: none;
      margin-top: 20px;
    }

    .header-image {
      margin: 20px auto;
      max-width: 200px;
      border-radius: 50%;
      border: 4px solid #fff;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    }
  </style>
</head>
<body>
  <!-- Ảnh trang trí -->
  <img src="https://images.unsplash.com/photo-1522276492355-8dc45e98ccb3?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&q=80&w=400" 
       alt="Hoa hồng bay trong gió" class="header-image">

  <div class="container">
    <h2>Nhập mật khẩu để mở khóa đoạn ghi âm</h2>
    <input type="password" id="password" placeholder="Nhập mật khẩu">
    <button onclick="unlockAudio()">Mở khóa</button>
    <div class="audio-container" id="audioContainer">
      <h3>Đoạn ghi âm của bạn:</h3>
      <audio controls>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
        Trình duyệt của bạn không hỗ trợ audio.
      </audio>
    </div>
  </div>

  <script>
    function unlockAudio() {
      const correctPassword = "iuemne"; // Thay bằng mật khẩu của bạn
      const inputPassword = document.getElementById("password").value;
      const audioContainer = document.getElementById("audioContainer");

      if (inputPassword === correctPassword) {
        audioContainer.style.display = "block"; // Hiển thị đoạn ghi âm
      } else {
        alert("Sai mật khẩu! Vui lòng thử lại.");
      }
    }
  </script>
</body>
</html>
