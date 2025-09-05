<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Mutant Academy V3.3</title>
  <style>
    body {
      font-family: 'Orbitron', sans-serif;
      background: linear-gradient(135deg, #0d1b2a, #1b263b);
      color: #fff;
      text-align: center;
      margin: 0;
      padding: 0;
    }
    .screen {
      display: none;
      padding: 20px;
    }
    #startScreen, #difficultyScreen, #powerScreen {
      display: block;
    }
    button {
      background: #1f4068;
      border: 2px solid #00adb5;
      color: #fff;
      padding: 10px 20px;
      margin: 10px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 8px;
    }
    button:hover {
      background: #00adb5;
    }
    .health-bar {
      width: 200px;
      height: 20px;
      background: #333;
      border-radius: 10px;
      margin: 10px auto;
      overflow: hidden;
    }
    .health-fill {
      height: 100%;
      background: #00ff00;
      width: 100%;
      transition: width 0.3s;
    }
    .floating-dmg {
      position: absolute;
      font-size: 20px;
      font-weight: bold;
      animation: floatUp 1s ease-out forwards;
      pointer-events: none;
    }
    @keyframes floatUp {
      from { opacity: 1; transform: translateY(0); }
      to { opacity: 0; transform: translateY(-40px); }
    }
    #gameArea {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin: 20px;
    }
    .character {
      font-size: 60px;
    }
    #inventory {
      margin-top: 15px;
      border: 1px solid #00adb5;
      padding: 10px;
      border-radius: 8px;
    }
  </style>
</head>
<body>
  <!-- Accueil -->
  <div id="startScreen" class="screen">
    <h1>🏛️ Mutant Academy</h1>
    <p>Bienvenue jeune mutant ! Choisis ta difficulté pour commencer l’entraînement.</p>
    <button onclick="showDifficulty()">Commencer</button>
  </div>

  <!-- Sélection difficulté -->
  <div id="difficultyScreen" class="screen">
    <h2>Choisis ta difficulté</h2>
    <label><input type="radio" name="difficulty" value="facile"> Facile</label><br>
    <label><input type="radio" name="difficulty" value="normal"> Normal</label><br>
    <label><input type="radio" name="difficulty" value="difficile"> Difficile</label><br>
    <button id="nextBtn">Suivant</button>
  </div>

  <!-- Sélection pouvoir -->
  <div id="powerScreen" class="screen">
    <h2>Choisis ton pouvoir</h2>
    <button onclick="choosePower('🔥 Feu')">🔥 Feu</button>
    <button onclick="choosePower('⚡ Électricité')">⚡ Électricité</button>
    <button onclick="choosePower('❄️ Glace')">❄️ Glace</button>
    <button onclick="choosePower('🧠 Télépathie')">🧠 Télépathie</button>
  </div>

  <!-- Jeu -->
  <div id="gameScreen" class="screen">
    <h2 id="stageTitle">Danger Room</h2>
    <div id="gameArea">
      <div>
        <div class="character" id="playerAvatar">🙂</div>
        <div class="health-bar"><div class="health-fill" id="playerHealth"></div></div>
        <p id="playerPV"></p>
      </div>
      <div>
        <div class="character" id="enemyAvatar">🤖</div>
        <div class="health-bar"><div class="health-fill" id="enemyHealth"></div></div>
        <p id="enemyPV"></p>
      </div>
    </div>
    <div id="actions">
      <button onclick="playerAttack()">Attaquer</button>
      <button onclick="useSpecial()">Pouvoir spécial</button>
      <button onclick="useItem()">Utiliser objet</button>
    </div>
    <div id="inventory">
      <h3>Inventaire</h3>
      <ul id="inventoryList"></ul>
    </div>
    <p id="log"></p>
  </div>

  <!-- Fin -->
  <div id="endScreen" class="screen">
    <h2 id="endTitle"></h2>
    <p id="endMessage"></p>
    <button onclick="location.reload()">Rejouer</button>
  </div>

  <script>
    const gameData = {
      difficulty: null,
      power: null,
      playerHP: 30,
      enemyHP: 20,
      inventory: [],
      specialUses: 2
    };

    function showDifficulty() {
      document.getElementById("startScreen").style.display = "none";
      document.getElementById("difficultyScreen").style.display = "block";
    }

    // Bouton suivant => aller à l’écran pouvoirs
    document.getElementById("nextBtn").addEventListener("click", () => {
      const diffChoice = document.querySelector("input[name='difficulty']:checked");
      if (!diffChoice) {
        alert("Choisis une difficulté !");
        return;
      }
      gameData.difficulty = diffChoice.value;
      document.getElementById("difficultyScreen").style.display = "none";
      document.getElementById("powerScreen").style.display = "block";
    });

    function choosePower(power) {
      gameData.power = power;
      document.getElementById("powerScreen").style.display = "none";
      startGame();
    }

    function startGame() {
      document.getElementById("gameScreen").style.display = "block";
      gameData.playerHP = 30;
      gameData.enemyHP = 20;
      gameData.inventory = ["💊 Sérum (+10 PV)", "🛡️ Bouclier (1 tour)"];
      updateUI();
      logMessage("Un robot d’entraînement apparaît !");
    }

    function updateUI() {
      const playerFill = document.getElementById("playerHealth");
      const enemyFill = document.getElementById("enemyHealth");
      document.getElementById("playerPV").textContent = "PV: " + gameData.playerHP;
      document.getElementById("enemyPV").textContent = "PV: " + gameData.enemyHP;
      playerFill.style.width = (gameData.playerHP / 30 * 100) + "%";
      enemyFill.style.width = (gameData.enemyHP / 20 * 100) + "%";
      const invList = document.getElementById("inventoryList");
      invList.innerHTML = "";
      gameData.inventory.forEach((item, i) => {
        const li = document.createElement("li");
        li.textContent = item;
        invList.appendChild(li);
      });
    }

    function logMessage(msg) {
      document.getElementById("log").textContent = msg;
    }

    function showFloatingDamage(amount, targetId) {
      const target = document.getElementById(targetId);
      const dmg = document.createElement("div");
      dmg.className = "floating-dmg";
      dmg.textContent = "-" + amount;
      dmg.style.color = "red";
      dmg.style.left = target.offsetLeft + 50 + "px";
      dmg.style.top = target.offsetTop + "px";
      document.body.appendChild(dmg);
      setTimeout(() => dmg.remove(), 1000);
    }

    function playerAttack() {
      const dmg = Math.floor(Math.random() * 6) + 3;
      gameData.enemyHP -= dmg;
      showFloatingDamage(dmg, "enemyAvatar");
      logMessage("Tu attaques et infliges " + dmg + " dégâts !");
      checkBattle();
      setTimeout(enemyAttack, 1000);
      updateUI();
    }

    function enemyAttack() {
      if (gameData.enemyHP <= 0) return;
      const dmg = Math.floor(Math.random() * 5) + 2;
      gameData.playerHP -= dmg;
      showFloatingDamage(dmg, "playerAvatar");
      logMessage("L’ennemi attaque et inflige " + dmg + " dégâts !");
      updateUI();
      checkBattle();
    }

    function useSpecial() {
      if (gameData.specialUses <= 0) {
        logMessage("Tu n’as plus de pouvoir spécial !");
        return;
      }
      const dmg = Math.floor(Math.random() * 10) + 8;
      gameData.enemyHP -= dmg;
      gameData.specialUses--;
      showFloatingDamage(dmg, "enemyAvatar");
      logMessage("🔥 Pouvoir spécial utilisé ! " + dmg + " dégâts !");
      updateUI();
      checkBattle();
      setTimeout(enemyAttack, 1000);
    }

    function useItem() {
      if (gameData.inventory.length === 0) {
        logMessage("Ton inventaire est vide !");
        return;
      }
      const item = gameData.inventory.shift();
      if (item.includes("💊")) {
        gameData.playerHP += 10;
        if (gameData.playerHP > 30) gameData.playerHP = 30;
        logMessage("Tu utilises un sérum, +10 PV !");
      } else if (item.includes("🛡️")) {
        logMessage("Tu actives un bouclier, prochain dégât réduit !");
        // Implémenter réduction plus tard
      }
      updateUI();
      setTimeout(enemyAttack, 1000);
    }

    function checkBattle() {
      if (gameData.enemyHP <= 0) {
        endGame(true);
      } else if (gameData.playerHP <= 0) {
        endGame(false);
      }
    }

    function endGame(victory) {
      document.getElementById("gameScreen").style.display = "none";
      document.getElementById("endScreen").style.display = "block";
      if (victory) {
        document.getElementById("endTitle").textContent = "Victoire 🎉";
        document.getElementById("endMessage").textContent = "Tu es désormais digne d’être un X-Men !";
      } else {
        document.getElementById("endTitle").textContent = "Défaite 💀";
        document.getElementById("endMessage").textContent = "Tu as échoué ton test, mais Xavier croit encore en toi.";
      }
    }
  </script>
</body>
</html>
