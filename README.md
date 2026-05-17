# Friends-savings-fund
PROJECT STRUCTURE

fundflow/
│
├── index.html
├── style.css
└── app.js
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>FundFlow</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>

  <div class="container">

    <h1>FundFlow Savings</h1>

    <div class="card">
      <h2>Total Savings</h2>
      <p id="total">0 SAR</p>
    </div>

    <div class="card">
      <h2>Add Member Deposit</h2>

      <input type="text" id="name" placeholder="Member Name" />
      <input type="number" id="amount" placeholder="Amount" />

      <button onclick="addDeposit()">
        Add Deposit
      </button>
    </div>

    <div class="card">
      <h2>Transaction History</h2>

      <ul id="history"></ul>
    </div>

  </div>

  <script src="app.js"></script>

</body>
</html>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f5f5f5;
}

.container {
  max-width: 500px;
  margin: auto;
  padding: 20px;
}

h1 {
  text-align: center;
  color: green;
}

.card {
  background: white;
  padding: 20px;
  margin-top: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

input {
  width: 100%;
  padding: 12px;
  margin-top: 10px;
  box-sizing: border-box;
}

button {
  width: 100%;
  padding: 12px;
  margin-top: 10px;
  background: green;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background: darkgreen;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  padding: 10px;
  border-bottom: 1px solid #ddd;
}
let total = 0;

function addDeposit() {

  const name = document.getElementById("name").value;
  const amount = Number(document.getElementById("amount").value);

  if (!name || !amount) {
    alert("Please enter all fields");
    return;
  }

  total += amount;

  document.getElementById("total").innerText =
    total + " SAR";

  const history = document.getElementById("history");

  const li = document.createElement("li");

  li.innerText =
    `${name} deposited ${amount} SAR`;

  history.prepend(li);

  document.getElementById("name").value = "";
  document.getElementById("amount").value = "";
}
