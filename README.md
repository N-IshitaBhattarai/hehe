
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Be My Valentine</title>
  <style>
    body {
      text-align: center;
      font-family: 'Arial', sans-serif;
      background-color: #f4c2c2; /* Baby pink */
      color: red;
      margin: 0;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 20px;
    }

    h1 {
      font-size: 2.5em;
      margin-bottom: 20px;
      text-shadow: 2px 2px 5px white;
    }

    input {
      padding: 10px;
      font-size: 16px;
      border-radius: 8px;
      border: 1px solid red;
      margin-bottom: 15px;
      width: 80%;
      max-width: 300px;
    }

    button {
      margin: 10px;
      padding: 15px 30px;
      font-size: 18px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: transform 0.2s, font-size 0.2s, padding 0.2s;
    }

    button:hover {
      transform: scale(1.1);
    }

    .yes {
      background-color: red;
      color: white;
    }

    .no {
      background-color: white;
      color: red;
    }

    #congratsMessage {
      font-size: 2em;
      color: white;
      background-color: red;
      padding: 15px;
      border-radius: 10px;
      margin-top: 20px;
      display: none;
    }

    /* Responsive Design */
    @media (max-width: 768px) {
      h1 {
        font-size: 2em;
      }
      button {
        font-size: 16px;
        padding: 12px 24px;
      }
    }

    @media (max-width: 480px) {
      h1 {
        font-size: 1.5em;
      }
      input {
        width: 100%;
      }
      button {
        font-size: 14px;
        padding: 10px 20px;
      }
    }
  </style>
</head>
<body>
  <h1 id="message">💖 Please enter your full name 💖</h1>
  <input type="text" id="nameInput" placeholder="Enter your name">
  <button onclick="askValentine()">Submit</button>

  <div id="valentineSection" style="display:none;">
    <h1 id="valentineMessage"></h1>
    <button class="yes" onclick="sayYes()">Yes</button>
    <button class="no" onclick="shrinkNo()">No</button>
    <div id="congratsMessage">Congratulationssssssssss 🎉❤️</div>
  </div>

  <script>
    function askValentine() {
      const name = document.getElementById('nameInput').value.trim();
      const section = document.getElementById('valentineSection');
      const msg = document.getElementById('valentineMessage');

      if (name.toLowerCase() === "nirmal sapkota") {
        msg.textContent = "💖 Nirmal Sapkota, will you be the Valentine of Ishita Bhattarai? 💖";
      } else {
        msg.textContent = "💖 Have a nice day 💖";
      }

      section.style.display = "block";
    }

    function sayYes() {
      document.getElementById('congratsMessage').style.display = "block";
    }

    function shrinkNo() {
      const noBtn = document.querySelector('.no');
      let currentSize = parseFloat(window.getComputedStyle(noBtn).fontSize);
      let currentPadding = parseFloat(window.getComputedStyle(noBtn).padding);

      if (currentSize > 5) {
        noBtn.style.fontSize = (currentSize - 2) + "px";
        noBtn.style.padding = (currentPadding - 2) + "px";
      } else {
        alert("Looks like you can’t say No anymore 💕");
      }
    }
  </script>
</body>
</html>
