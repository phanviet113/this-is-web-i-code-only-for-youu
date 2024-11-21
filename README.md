<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bông Hoa Hoàng Chấm và Cảnh Nền 3D</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      text-align: center;
      background: url('https://images.unsplash.com/photo-1562901243-8b0a68c9f61f') no-repeat center center fixed;
      background-size: cover;
      overflow: hidden;
      height: 100vh;
      position: relative;
      animation: backgroundAnimation 60s infinite linear;
    }

    /* Nền với hiệu ứng 3D */
    @keyframes backgroundAnimation {
      0% { transform: translateZ(0) rotate(0deg); }
      100% { transform: translateZ(150px) rotate(360deg); }
    }

    .hill {
      position: absolute;
      bottom: 0;
      width: 100%;
      height: 200px;
      background: #228B22;
      border-top-left-radius: 50% 50%;
      border-top-right-radius: 50% 50%;
    }

    .container {
      position: absolute;
      top: 30%;
      left: 50%;
      transform: translate(-50%, -50%);
      padding: 20px;
      background: rgba(255, 255, 255, 0.7);
      border-radius: 10px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
      text-align: center;
    }

    input[type="password"] {
      padding: 10px;
      width: 80%;
      margin: 10px 0;
      border: 2px solid #d81b60;
      border-radius: 5px;
    }

    button {
      padding: 10px 20px;
      border: none;
      background-color: #d81b60;
      color: white;
      border-radius: 5px;
      font-size: 1em;
      cursor: pointer;
    }

    button:hover {
      background-color: #ad1457;
    }

    /* Hoa Hoàng Chấm */
    .flower {
      position: absolute;
      bottom: 0;
      width: 30px;
      height: 30px;
      display: flex;
      justify-content: center;
      align-items: center;
      animation: grow 4s ease-in-out forwards, move 5s ease-in-out infinite;
    }

    .flower .petal {
      position: absolute;
      width: 12px;
      height: 12px;
      border-radius: 50%;
      background-color: yellow;
      animation: petalAnimation 1s ease-in-out infinite;
    }

    .flower .petal:nth-child(1) { transform: rotate(0deg) translateX(15px); }
    .flower .petal:nth-child(2) { transform: rotate(90deg) translateX(15px); }
    .flower .petal:nth-child(3) { transform: rotate(180deg) translateX(15px); }
    .flower .petal:nth-child(4) { transform: rotate(270deg) translateX(15px); }

    @keyframes grow {
      0% {
        transform: scale(0);
        bottom: 0;
      }
      50% {
        transform: scale(1);
        bottom: 40%;
      }
      100% {
        transform: scale(1.2);
        bottom: 70%;
        background-color: yellow;
      }
    }

    @keyframes move {
      0% { transform: translateX(0); }
      50% { transform: translateX(30px); }
      100% { transform: translateX(-30px); }
    }

    @keyframes petalAnimation {
      0% { transform: scale(1); }
      50% { transform: scale(1.2); }
      100% { transform: scale(1); }
    }

    #message {
      margin-top: 20px;
      font-size: 1.5em;
      color: #d81b60;
      display: none;
    }
  </style>
</head>
<body>
  <div class="hill"></div>
  <div class="container">
    <h2>Nhập mật khẩu để mở bí mật</h2>
    <input type="password" id="password" placeholder="Nhập mật khẩu">
    <button onclick="unlockMessage()">Mở khóa</button>
    <p id="message">Hôm nay là ngày 21 tháng 11 năm 2024, và anh muốn viết những dòng này cho em từ bây giờ vì anh muốn chuẩn bị thật tốt cho mọi thứ. Em là người đặc biệt với anh, và anh cũng muốn món quà này dành cho em phải thật sự đặc biệt.

Anh hy vọng rằng vào ngày 3/12, chúng ta sẽ chính thức bước vào một mối quan hệ mới. Nếu mọi thứ diễn ra tốt đẹp, đó sẽ là thời điểm mà chúng ta bắt đầu cùng nhau, không chỉ là những cuộc trò chuyện nữa mà là sự đồng hành thật sự. Anh rất vui và hạnh phúc vì em đã đến bên anh, cho anh cơ hội để yêu thương và quan tâm em.

Anh hiểu rằng trong một mối quan hệ, không phải lúc nào cũng hoàn hảo. Sẽ có những lúc chúng ta không đồng quan điểm, nhưng anh mong rằng thay vì cãi nhau, chúng ta sẽ luôn tìm cách trò chuyện và hiểu nhau hơn. Nếu em gặp phải bất kỳ điều gì khiến em buồn hoặc khó chịu, đừng ngần ngại chia sẻ với anh. Anh luôn sẵn sàng lắng nghe và ở đây để cùng em vượt qua mọi khó khăn.

Cuộc sống sẽ không phải lúc nào cũng dễ dàng. Công việc, học tập, gia đình… những vấn đề đó đôi khi có thể làm chúng ta cảm thấy căng thẳng và mệt mỏi. Nhưng anh hy vọng chúng ta sẽ luôn bên nhau để giúp đỡ nhau, thay vì để những áp lực đó làm ảnh hưởng đến chúng ta. Em luôn có anh ở đây, sẵn sàng hỗ trợ khi em cần.

Cảm ơn em vì đã đọc những dòng này. Anh yêu em, rất nhiều.</p>
  </div>

  <script>
    function unlockMessage() {
      const correctPassword = "iuemnhieu";
      const inputPassword = document.getElementById("password").value;
      const message = document.getElementById("message");

      if (inputPassword === correctPassword) {
        message.style.display = "block";
        createFlowers();
      } else {
        alert("Sai mật khẩu! Vui lòng thử lại.");
      }
    }

    function createFlowers() {
      for (let i = 0; i < 30; i++) {
        const flower = document.createElement("div");
        flower.className = "flower";
        flower.style.left = `${Math.random() * 100}%`;
        flower.style.animationDelay = `${Math.random() * 2}s`;
        
        // Create petals for the flower
        for (let j = 0; j < 4; j++) {
          const petal = document.createElement("div");
          petal.className = "petal";
          flower.appendChild(petal);
        }

        document.body.appendChild(flower);
      }
    }
  </script>
</body>
</html>
  
