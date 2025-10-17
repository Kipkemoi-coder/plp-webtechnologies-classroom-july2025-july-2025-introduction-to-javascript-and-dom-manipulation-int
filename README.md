#Assignment: Mastering JavaScript Fundamentals
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>GTA JavaScript Fundamentals</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      line-height: 1.6;
      margin: 0;
      padding: 0;
      background: #111;
      color: #eee;
    }
    header, footer {
      background: #000;
      color: #ff2a2a;
      text-align: center;
      padding: 1rem;
      font-weight: bold;
      letter-spacing: 1px;
    }
    main {
      padding: 1rem 2rem;
    }
    section {
      background: #1c1c1c;
      margin: 1rem 0;
      padding: 1rem;
      border-radius: 6px;
      border: 1px solid #ff2a2a;
      box-shadow: 0 2px 5px rgba(0,0,0,0.6);
    }
    h2 {
      color: #ff2a2a;
    }
    button {
      margin-top: 0.5rem;
      padding: 0.5rem 1rem;
      border: none;
      background: #ff2a2a;
      color: white;
      border-radius: 4px;
      cursor: pointer;
    }
    button:hover {
      background: #cc0000;
    }
    ul {
      margin-top: 0.5rem;
      padding-left: 20px;
    }
    .default-background {
      background: #111;
    }
    .alt-background {
      background: #222;
    }
  </style>
</head>
<body class="default-background">
  <header>
    <h1>GTA JavaScript Fundamentals</h1>
    <p>Learn coding while riding the chaos of Los Santos.</p>
  </header>

  <main>
    <section>
      <h2>Part 1: Basics</h2>
      <label for="ageInput">Enter your age:</label>
      <input type="number" id="ageInput" placeholder="Enter age">
      <button id="checkAgeBtn">Check Age</button>
      <p id="ageResult"></p>
    </section>

    <section>
      <h2>Part 2: Functions</h2>
      <label for="num1">Number 1:</label>
      <input type="number" id="num1" placeholder="Enter first number">
      <label for="num2">Number 2:</label>
      <input type="number" id="num2" placeholder="Enter second number">
      <button id="sumBtn">Calculate Sum</button>
      <p id="sumResult"></p>
    </section>

    <section>
      <h2>Part 3: Loops</h2>
      <button id="countdownBtn">Start Countdown (5 → 1)</button>
      <ul id="countdownList"></ul>
      <button id="showArrayBtn">Show GTA Games</button>
      <ul id="gamesList"></ul>
    </section>

    <section>
      <h2>Part 4: DOM</h2>
      <button id="toggleColorBtn">Toggle Background</button>
      <button id="addItemBtn">Add New Item</button>
      <ul id="dynamicList">
        <li>First Mission</li>
      </ul>
      <p id="message">Click below to change me.</p>
      <button id="changeTextBtn">Change Text</button>
    </section>
  </main>

  <footer>
    <p>&copy; 2025 GTA Coder’s Edition</p>
  </footer>

  <script>
    document.getElementById("checkAgeBtn").addEventListener("click", () => {
      const age = parseInt(document.getElementById("ageInput").value);
      const result = document.getElementById("ageResult");
      if (!age) {
        result.textContent = "Enter a valid age.";
      } else if (age >= 18) {
        result.textContent = "Welcome to Los Santos, outlaw!";
      } else {
        result.textContent = "Too young, rookie. Stick to arcade games.";
      }
    });

    function addNumbers(a, b) {
      return a + b;
    }
    function displaySum() {
      const num1 = parseFloat(document.getElementById("num1").value);
      const num2 = parseFloat(document.getElementById("num2").value);
      const sum = addNumbers(num1, num2);
      document.getElementById("sumResult").textContent = `Total: ${sum}`;
    }
    document.getElementById("sumBtn").addEventListener("click", displaySum);

    document.getElementById("countdownBtn").addEventListener("click", () => {
      const list = document.getElementById("countdownList");
      list.innerHTML = "";
      for (let i = 5; i >= 1; i--) {
        const li = document.createElement("li");
        li.textContent = i;
        list.appendChild(li);
      }
    });

    const games = ["GTA III", "GTA Vice City", "GTA San Andreas", "GTA V"];
    document.getElementById("showArrayBtn").addEventListener("click", () => {
      const list = document.getElementById("gamesList");
      list.innerHTML = "";
      games.forEach(game => {
        const li = document.createElement("li");
        li.textContent = game;
        list.appendChild(li);
      });
    });

    document.getElementById("toggleColorBtn").addEventListener("click", () => {
      document.body.classList.toggle("alt-background");
    });

    document.getElementById("addItemBtn").addEventListener("click", () => {
      const newItem = document.createElement("li");
      newItem.textContent = "New Mission Added!";
      document.getElementById("dynamicList").appendChild(newItem);
    });

    document.getElementById("changeTextBtn").addEventListener("click", () => {
      document.getElementById("message").textContent = "Mission Updated: Time to roll out!";
    });
  </script>
</body>
</html>


