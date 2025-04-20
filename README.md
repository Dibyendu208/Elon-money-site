<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Spend Elon Musk's Money</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: Arial, sans-serif; background: #f4f4f4; padding: 20px; }
    header { text-align: center; margin-bottom: 20px; }
    h1 { font-size: 2.5rem; color: #333; }
    .balance { font-size: 1.5rem; margin: 10px 0; color: green; }
    .store { display: flex; flex-wrap: wrap; gap: 20px; justify-content: center; }
    .item {
      background: white;
      border-radius: 10px;
      padding: 20px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
      width: 200px;
      text-align: center;
    }
    .item img { width: 100%; height: 120px; object-fit: contain; }
    .item h2 { font-size: 1.2rem; margin: 10px 0; }
    .item p { margin: 5px 0; }
    .item button {
      background: #007bff;
      color: white;
      border: none;
      padding: 10px;
      cursor: pointer;
      border-radius: 5px;
    }
    .item button:hover { background: #0056b3; }
  </style>
</head>
<body>
  <header>
    <h1>Spend Elon Musk's Money</h1>
    <div class="balance">Balance: $<span id="balance">234000000000</span></div>
  </header>
  <main class="store" id="store"></main>  <script>
    const items = [
      { name: "Big Mac", price: 5, img: "https://neal.fun/spend/images/big-mac.jpg" },
      { name: "Tesla Model S", price: 80000, img: "https://neal.fun/spend/images/tesla.jpg" },
      { name: "Private Jet", price: 15000000, img: "https://neal.fun/spend/images/private-jet.jpg" },
      { name: "iPhone", price: 999, img: "https://neal.fun/spend/images/iphone.jpg" },
      { name: "Netflix Subscription", price: 15, img: "https://neal.fun/spend/images/netflix.jpg" },
      { name: "Gaming PC", price: 2500, img: "https://neal.fun/spend/images/gaming-pc.jpg" },
      { name: "Mansion", price: 5000000, img: "https://neal.fun/spend/images/mansion.jpg" },
      { name: "F1 Car", price: 2000000, img: "https://neal.fun/spend/images/f1-car.jpg" },
      { name: "Superyacht", price: 75000000, img: "https://neal.fun/spend/images/yacht.jpg" },
      { name: "Island", price: 100000000, img: "https://neal.fun/spend/images/island.jpg" },
      { name: "Movie Studio", price: 250000000, img: "https://neal.fun/spend/images/movie-studio.jpg" },
      { name: "Football Team", price: 3000000000, img: "https://neal.fun/spend/images/football-team.jpg" }
    ];

    let balance = 234000000000;
    const balanceDisplay = document.getElementById("balance");
    const store = document.getElementById("store");

    function updateBalanceDisplay() {
      balanceDisplay.textContent = balance.toLocaleString();
    }

    function buyItem(price) {
      if (balance >= price) {
        balance -= price;
        updateBalanceDisplay();
      } else {
        alert("Not enough money!");
      }
    }

    items.forEach(item => {
      const el = document.createElement("div");
      el.className = "item";
      el.innerHTML = `
        <img src="${item.img}" alt="${item.name}" />
        <h2>${item.name}</h2>
        <p>Price: $${item.price.toLocaleString()}</p>
        <button onclick="buyItem(${item.price})">Buy</button>
      `;
      store.appendChild(el);
    });

    updateBalanceDisplay();
  </script></body>
</html> 
