<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Apple Premium Store</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
}

body{
    background:#000;
    color:white;
    overflow-x:hidden;
}

/* Navbar */
nav{
    position:fixed;
    top:0;
    width:100%;
    background:rgba(0,0,0,0.8);
    backdrop-filter:blur(15px);
    display:flex;
    justify-content:space-between;
    align-items:center;
    padding:20px 8%;
    z-index:1000;
}

.logo{
    font-size:28px;
    font-weight:700;
}

nav ul{
    display:flex;
    list-style:none;
    gap:30px;
}

nav ul li a{
    color:white;
    text-decoration:none;
    transition:.3s;
}

nav ul li a:hover{
    color:#999;
}

/* Hero */
.hero{
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    text-align:center;
    flex-direction:column;
    background:linear-gradient(to bottom,#000,#111);
}

.hero h1{
    font-size:70px;
    margin-bottom:15px;
}

.hero p{
    font-size:22px;
    color:#aaa;
    margin-bottom:25px;
}

.btn{
    padding:14px 35px;
    background:white;
    color:black;
    border:none;
    border-radius:40px;
    font-size:16px;
    cursor:pointer;
    transition:.3s;
}

.btn:hover{
    transform:scale(1.05);
}

/* Products */
.products{
    padding:120px 8%;
}

.section-title{
    text-align:center;
    font-size:50px;
    margin-bottom:60px;
}

.product-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
    gap:30px;
}

.card{
    background:#111;
    border-radius:25px;
    padding:25px;
    text-align:center;
    transition:.4s;
}

.card:hover{
    transform:translateY(-10px);
    box-shadow:0 0 30px rgba(255,255,255,.15);
}

.card img{
    width:100%;
    max-width:250px;
    margin-bottom:20px;
}

.card h3{
    margin-bottom:10px;
}

.price{
    color:#ddd;
    font-size:22px;
    margin-bottom:15px;
}

.buy-btn{
    background:white;
    color:black;
    border:none;
    padding:12px 25px;
    border-radius:30px;
    cursor:pointer;
}

/* Cart */
.cart{
    position:fixed;
    right:20px;
    bottom:20px;
    background:white;
    color:black;
    width:280px;
    border-radius:20px;
    padding:20px;
    box-shadow:0 10px 40px rgba(0,0,0,.4);
}

.cart h3{
    margin-bottom:10px;
}

#cartItems{
    margin-bottom:15px;
}

.total{
    font-weight:bold;
    font-size:20px;
}

/* Footer */
footer{
    text-align:center;
    padding:40px;
    color:#888;
}

@media(max-width:768px){
    .hero h1{
        font-size:45px;
    }

    .section-title{
        font-size:36px;
    }

    nav ul{
        display:none;
    }
}
</style>
</head>
<body>

<nav>
    <div class="logo"> Apple Store</div>

    <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#products">iPhone</a></li>
        <li><a href="#">Accessories</a></li>
        <li><a href="#">Support</a></li>
    </ul>
</nav>

<section class="hero">
    <h1>iPhone 17 Pro</h1>
    <p>Built for Apple Intelligence.</p>
    <button class="btn" onclick="document.getElementById('products').scrollIntoView({behavior:'smooth'})">
        Shop Now
    </button>
</section>

<section class="products" id="products">

    <h2 class="section-title">Featured iPhones</h2>

    <div class="product-grid">

        <div class="card">
            <img src="https://images.unsplash.com/photo-1592750475338-74b7b21085ab?w=600" alt="">
            <h3>iPhone 17 Pro Max</h3>
            <div class="price">$1499</div>
            <button class="buy-btn" onclick="addToCart('iPhone 17 Pro Max',1499)">
                Add to Cart
            </button>
        </div>

        <div class="card">
            <img src="https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?w=600" alt="">
            <h3>iPhone 17 Pro</h3>
            <div class="price">$1299</div>
            <button class="buy-btn" onclick="addToCart('iPhone 17 Pro',1299)">
                Add to Cart
            </button>
        </div>

        <div class="card">
            <img src="https://images.unsplash.com/photo-1580910051074-3eb694886505?w=600" alt="">
            <h3>iPhone 17</h3>
            <div class="price">$999</div>
            <button class="buy-btn" onclick="addToCart('iPhone 17',999)">
                Add to Cart
            </button>
        </div>

    </div>

</section>

<div class="cart">
    <h3>🛒 Cart</h3>
    <div id="cartItems">No items yet</div>
    <div class="total">Total: $<span id="total">0</span></div>
</div>

<footer>
    © 2026 Apple Premium Store. Premium Shopping Experience.
</footer>

<script>
let total = 0;
let items = [];

function addToCart(name, price){

    items.push(name);
    total += price;

    document.getElementById("cartItems").innerHTML =
        items.map(item => "• " + item).join("<br>");

    document.getElementById("total").innerText = total;

    alert(name + " added to cart!");
}
</script>

</body>
</html>
