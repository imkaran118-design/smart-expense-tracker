<!DOCTYPE html>
<html>
<head>
  <title>Smart Expense Tracker</title>

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      padding: 20px;
    }

    .box {
      max-width: 500px;
      margin: auto;
      background: white;
      padding: 25px;
      border-radius: 15px;
    }

    input {
      width: 100%;
      padding: 12px;
      margin: 8px 0;
      box-sizing: border-box;
    }

    button {
      padding: 12px 20px;
      margin-top: 8px;
      cursor: pointer;
    }

    #result {
      margin-top: 20px;
      font-size: 18px;
      font-weight: bold;
    }
  </style>
</head>

<body>

<div class="box">

  <h1>💰 Smart Expense Tracker</h1>

  <p>Track your expenses easily 🚀</p>

  <h2>Add Expense</h2>

  <input id="name" type="text" placeholder="Expense name">

  <input id="amount" type="number" placeholder="Amount">

  <button id="addBtn">Add Expense</button>

  <div id="result">
    Total: ₹0
  </div>

  <ul id="list"></ul>

</div>

<script>
  let total = 0;

  document.getElementById("addBtn").addEventListener("click", function() {

    let name = document.getElementById("name").value;
    let amount = Number(document.getElementById("amount").value);

    if (name === "" || amount <= 0) {
      alert("Please enter expense name and amount!");
      return;
    }

    total = total + amount;

    document.getElementById("result").innerText =
      "Total: ₹" + total;

    let item = document.createElement("li");

    item.innerText = name + " — ₹" + amount;

    document.getElementById("list").appendChild(item);

    document.getElementById("name").value = "";
    document.getElementById("amount").value = "";

  });
</script>

</body>
</html>
