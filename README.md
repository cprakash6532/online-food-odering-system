# online-food-odering-system
An Online Food Ordering System is a website or application that helps people order food easily through the internet without visiting a restaurant. It allows customers to choose their favourite food from different restaurants and place orders from home, college, or office. First, customers need to register or log in to the website. After logging in, they can view the food menu, check food names, prices, images, and descriptions. They can select the food items they like and add them to the shopping cart. They can also increase or decrease the quantity of food items and remove unwanted items from the cart.

After selecting the food, customers can enter their delivery address and place the order. They can pay using online payment methods or choose cash on delivery. Customers can also track their orders and know whether the order is confirmed, preparing, or out for delivery.

The admin can manage food items, update prices, add new dishes, view customer details, and manage orders. Restaurant owners can easily receive and process customer orders through this system.

The main purpose of this project is to make food ordering simple, fast, and convenient. It saves time, reduces manual work, avoids confusion in taking orders, and provides a better experience for both customers and restaurant owners.


<!DOCTYPE html>
<html>
<head>
    <title>Online Food Ordering System</title>
    <style>
        body {
            font-family: Arial;
            background: #f5f5f5;
            margin: 0;
            text-align: center;
        }

        header {
            background: #ff5722;
            color: white;
            padding: 20px;
        }

        .menu {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            padding: 20px;
        }

        .food {
            background: white;
            padding: 15px;
            width: 200px;
            border-radius: 10px;
            box-shadow: 0 2px 8px #ccc;
        }

        button {
            background: #ff5722;
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            border-radius: 5px;
        }

        button:hover {
            background: #e64a19;
        }

        #cart {
            background: white;
            margin: 20px auto;
            padding: 20px;
            max-width: 400px;
            border-radius: 10px;
        }
    </style>
</head>

<body>

<header>
    <h1>Online Food Ordering System</h1>
    <p>Order Your Favourite Food Online!</p>
</header>

<h2>Our Food Menu</h2>

<div class="menu">

    <div class="food">
        <h3>Pizza</h3>
        <p>Price: ₹150</p>
        <button onclick="addToCart('Pizza',150)">
            Add to Cart
        </button>
    </div>

    <div class="food">
        <h3>Burger</h3>
        <p>Price: ₹100</p>
        <button onclick="addToCart('Burger',100)">
            Add to Cart
        </button>
    </div>

    <div class="food">
        <h3>Biryani</h3>
        <p>Price: ₹180</p>
        <button onclick="addToCart('Biryani',180)">
            Add to Cart
        </button>
    </div>

    <div class="food">
        <h3>Sandwich</h3>
        <p>Price: ₹80</p>
        <button onclick="addToCart('Sandwich',80)">
            Add to Cart
        </button>
    </div>

</div>

<div id="cart">
    <h2>Shopping Cart</h2>
    <ul id="cartItems"></ul>
    <h3>Total: ₹<span id="total">0</span></h3>
    <button onclick="placeOrder()">Place Order</button>
</div>

<script>
    let total = 0;

    function addToCart(name, price) {
        let item = document.createElement("li");
        item.textContent = name + " - ₹" + price;

        document.getElementById("cartItems")
            .appendChild(item);

        total += price;

        document.getElementById("total")
            .textContent = total;
    }

    function placeOrder() {
        if (total === 0) {
            alert("Please select some food items!");
        } else {
            alert("Your order has been placed successfully!");
            document.getElementById("cartItems").innerHTML = "";
            total = 0;
            document.getElementById("total").textContent = total;
        }
    }
</script>

</body>
</html>

