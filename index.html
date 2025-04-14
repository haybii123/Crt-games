<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Caretaker Squad Slot Game</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      font-family: 'Orbitron', sans-serif;
      background: linear-gradient(135deg, #1e1e1e, #3a3a3a);
      color: white;
      overflow: hidden;
    }
    #loading {
      position: fixed;
      top: 0; left: 0; right: 0; bottom: 0;
      background: black;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 3rem;
      color: #d4af37;
      font-weight: bold;
      text-shadow: 2px 2px 8px #8b6f20;
      z-index: 9999;
    }
    #game {
      display: none;
      padding: 20px;
      text-align: center;
    }
    #slot {
      display: grid;
      grid-template-columns: repeat(5, 80px);
      grid-template-rows: repeat(4, 80px);
      gap: 10px;
      justify-content: center;
      margin: 20px auto;
      background: #00000066;
      padding: 10px;
      border-radius: 15px;
    }
    .cell {
      width: 80px;
      height: 80px;
      background: #222;
      font-size: 2rem;
      display: flex;
      justify-content: center;
      align-items: center;
      border-radius: 10px;
      transition: background 0.5s;
    }
    .blink {
      animation: blink 0.5s infinite alternate;
    }
    .spin-effect {
      animation: spinEffect 0.3s ease-in-out;
    }
    @keyframes blink {
      from { background: #444; }
      to { background: yellow; color: black; }
    }
    @keyframes spinEffect {
      0% { transform: scale(1); opacity: 0.2; }
      50% { transform: scale(1.2); opacity: 0.6; }
      100% { transform: scale(1); opacity: 1; }
    }
    #controls {
      margin-top: 20px;
    }
    button {
      padding: 10px 20px;
      font-size: 1rem;
      background: #28a745;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-family: 'Orbitron', sans-serif;
    }
    button:disabled {
      background: gray;
      cursor: not-allowed;
    }
    #message {
      margin-top: 15px;
      font-size: 1.1rem;
    }
  </style>
</head>
<body>
  <div id="loading">CARETAKER SQUAD</div>

  <div id="game">
    <div>Coins: <span id="coins">500</span> | Bonus Spins: <span id="bonus">0</span></div>
    <div id="slot"></div>
    <div id="controls">
      <button id="spinBtn">SPIN (10 coins)</button>
    </div>
    <div id="message"></div>
  </div>

  <audio id="bgm" loop>
    <source src="bgm.mp3" type="audio/mpeg">
  </audio>
  <audio id="winSound">
    <source src="win.mp3" type="audio/mpeg">
  </audio>
  <audio id="jackpotSound">
    <source src="jackpot.mp3" type="audio/mpeg">
  </audio>
  <audio id="bonusSound">
    <source src="bonus.mp3" type="audio/mpeg">
  </audio>

  <script>
    const slot = document.getElementById("slot");
    const spinBtn = document.getElementById("spinBtn");
    const coinsDisplay = document.getElementById("coins");
    const bonusDisplay = document.getElementById("bonus");
    const message = document.getElementById("message");
    const symbols = ['🦖','🦕','🦎','🦟','🦀','🦓','🐃'];
    const symbolValues = {
      '🦖': 50,
      '🦕': 40,
      '🦎': 30,
      '🦟': 20,
      '🦀': 10,
      '🦓': 100,
      '🐃': 5
    };

    let coins = 500;
    let bonusSpins = 0;
    let autoSpinning = false;

    const rows = 4;
    const cols = 5;
    for (let i = 0; i < rows * cols; i++) {
      const div = document.createElement("div");
      div.className = "cell";
      slot.appendChild(div);
    }

    const cells = document.querySelectorAll(".cell");

    function getRandomSymbol() {
      return symbols[Math.floor(Math.random() * symbols.length)];
    }

    async function spin() {
      if (coins < 10 && bonusSpins === 0) return;

      if (bonusSpins === 0) coins -= 10;
      else bonusSpins--;

      coinsDisplay.textContent = coins;
      bonusDisplay.textContent = bonusSpins;
      spinBtn.disabled = true;
      message.textContent = "Spinning...";

      let resultGrid = [];

      // Tampilkan animasi acak terlebih dahulu (simulasi spin visual)
      for (let i = 0; i < 10; i++) {
        for (let row = 0; row < rows; row++) {
          for (let col = 0; col < cols; col++) {
            const tempSym = getRandomSymbol();
            const idx = row * cols + col;
            const cell = cells[idx];
            cell.textContent = tempSym;
          }
        }
        await new Promise(r => setTimeout(r, 100));
      }

      // Sekarang hasil akhir
      for (let row = 0; row < rows; row++) {
        resultGrid[row] = [];
        for (let col = 0; col < cols; col++) {
          const sym = getRandomSymbol();
          resultGrid[row][col] = sym;
          const idx = row * cols + col;
          const cell = cells[idx];
          cell.classList.remove("blink");
          cell.classList.add("spin-effect");
          cell.textContent = sym;
        }
      }

      setTimeout(() => {
        cells.forEach(cell => cell.classList.remove("spin-effect"));
      }, 300);

      await new Promise(res => setTimeout(res, 1000));
      await checkWin(resultGrid);
      spinBtn.disabled = false;

      if (bonusSpins > 0 && autoSpinning) {
        message.textContent = `Bonus Spin ${10 - bonusSpins}/10`;
        setTimeout(spin, 1000);
      } else if (bonusSpins > 0) {
        autoSpinning = true;
        message.textContent = `Bonus Spin 1/10`;
        setTimeout(spin, 1000);
      } else {
        autoSpinning = false;
      }
    }

    async function checkWin(grid) {
      let won = false;
      let totalWin = 0;
      for (let col = 0; col <= cols - 5; col++) {
        for (let row = 0; row < rows; row++) {
          const match = grid[row].slice(col, col + 5);
          if (match.every((s) => s === match[0])) {
            won = true;
            const sym = match[0];
            const value = symbolValues[sym] || 0;
            totalWin += value * 5;

            if (sym === '🦓') document.getElementById('jackpotSound').play();
            else if (sym === '🐃') {
              bonusSpins += 10;
              document.getElementById('bonusSound').play();
            } else document.getElementById('winSound').play();

            for (let i = 0; i < 5; i++) {
              const idx = row * cols + col + i;
              cells[idx].classList.add("blink");
            }
          }
        }
      }

      if (won) {
        coins += totalWin;
        coinsDisplay.textContent = coins;
        bonusDisplay.textContent = bonusSpins;
        message.textContent = `You won ${totalWin} coins!`;
        await new Promise(res => setTimeout(res, 5000));
        message.textContent = "";
      } else {
        message.textContent = "No win. Try again!";
        await new Promise(res => setTimeout(res, 2000));
        message.textContent = "";
      }
    }

    spinBtn.addEventListener("click", spin);

    setTimeout(() => {
      document.getElementById("loading").style.display = "none";
      document.getElementById("game").style.display = "block";
      document.getElementById("bgm").play();
    }, 10000);
  </script>
</body>
</html>
