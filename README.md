<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Smart Expense Tracker</title>

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      margin: 0;
      padding: 20px;
    }

    .container {
      max-width: 500px;
      margin: auto;
      background: white;
      padding: 25px;
      border-radius: 15px;
    }

    h1 {
      text-align: center;
    }

    input, button {
      width: 100%;
      padding: 12px;
      margin-top: 10px;
      box-sizing: border-box;
    }

    button {
      cursor: pointer;
      font-size: 16px;
    }

    .total {
      margin-top: 20px;
      font-size: 20px;
      font-weight: bold;
    }

    li {
      margin-top: 10px;
      padding: 10px;
      background: #f1f1f1;
      list-style: none;
    }
  </style>
</head>

<body>

  <div class="container">

    <h1>💰 Smart Expense Tracker</h1>

    <p>Track your expenses easily 🚀</p>

    <input id="expenseName" type="text" placeholder="Expense name">

    <input id="expenseAmount" type="number" placeholder="Amount">

    <button onclick="addExpense()">Add Expense</button>

    <div class="total">
      Total: ₹<span id="total">0</span>
    </div>

    <ul id="expenseList"></ul>

  </div>

  <script>
    let total = 0;

    function addExpense() {

      const name = document.getElementById("expenseName").value;
      const amount = Number(document.getElementById("expenseAmount").value);

      if (name === "" || amount <= 0) {
        alert("Please enter expense name and amount!");
        return;
      }

      total += amount;

      document.getElementById("total").textContent = total;

      const list = document.getElementById("expenseList");

      const item = document.createElement("li");

      item.textContent = name + " — ₹" + amount;

      list.appendChild(item);

      document.getElementById("expenseName").value = "";
      document.getElementById("expenseAmount").value = "";
    }
  </script>

</body>
</html>
