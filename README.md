<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Spend Elon's Fortune</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        .item {
            display: flex;
            justify-content: space-between;
            width: 300px;
            margin: 10px auto;
            padding: 10px;
            border: 1px solid black;
            border-radius: 5px;
        }
        button {
            background-color: green;
            color: white;
            border: none;
            padding: 5px 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Spend Elon's Fortune</h1>
    <h2>Money Left: <span id="money">240000000000</span> $</h2>
    
    <div id="items"></div>
    
    <script>
        let money = 240000000000;
        const moneyDisplay = document.getElementById("money");
        const itemsContainer = document.getElementById("items");

        const items = [
            { name: "Ferrari", price: 250000 },
            { name: "Private Jet", price: 50000000 },
            { name: "Luxury Mansion", price: 150000000 },
            { name: "PS5", price: 500 },
        ];

        function buyItem(price) {
            if (money >= price) {
                money -= price;
                moneyDisplay.textContent = money;
            } else {
                alert("Not enough money!");
            }
        }

        items.forEach(item => {
            const div = document.createElement("div");
            div.classList.add("item");
            div.innerHTML = `
                <span>${item.name} - $${item.price}</span>
                <button onclick="buyItem(${item.price})">Buy</button>
            `;
            itemsContainer.appendChild(div);
        });
    </script>
</body>
</html>
