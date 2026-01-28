# My-website-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Mobile Recharge</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="container">
    <h2>📲 Mobile Recharge</h2>

    <input type="tel" id="mobile" placeholder="Enter Mobile Number" maxlength="10">

    <select id="operator">
        <option value="">Select Operator</option>
        <option>Airtel</option>
        <option>Jio</option>
        <option>VI</option>
        <option>BSNL</option>
    </select>




    <input type="number" id="amount" placeholder="Enter Amount">

    <button onclick="recharge()">Recharge Now</button>

    <p id="msg"></p>
</div>

<script src="script.js"></script>
</body>
</html>
<!DOCTYPE html>
<html>
<head>
    <secondpage>
    <title>Login</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="box">
    <h2>Login</h2>

    <input type="email" id="loginEmail" placeholder="Email">
    <input type="password" id="loginPassword" placeholder="Password">

    <button onclick="login()">Login</button>

    <firstpagel></firstpagel>
    <p>New user? <a href="signup.html">Signup</a></p>
    <p id="loginMsg"></p>
</div>

<script src="script.js"></script>
</body>
</html>
<!DOCTYPE html>
<html>
<head>
    <title>Paytm UPI Payment</title>
</head>
<body style="font-family:Arial;background:#f2f2f2;">

<div style="width:300px;margin:80px auto;background:#fff;padding:20px;border-radius:10px;">
    <h3>Paytm UPI Recharge</h3>

    <form method="post" action="paytm.php">
        <input type="number" name="amount" placeholder="Enter Amount"
            style="width:100%;padding:10px;margin-bottom:10px;" required>

        <button type="submit"
            style="width:100%;padding:12px;background:#00baf2;color:#fff;border:none;border-radius:5px;">
            Pay via Paytm UPI
        </button>
    </form>
</div>

</body>
</html>
<!DOCTYPE html>
<html>
<head>
    <title>Signup</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="box">
    <h2>Create Account</h2>

    <input type="text" id="name" placeholder="Full Name">
    <input type="email" id="email" placeholder="Email">
    <input type="password" id="password" placeholder="Password">

    <button onclick="signup()">Signup</button>

    <p>Already have account? <a href="index.html">Login</a></p>
    <p id="msg"></p>
</div>

<script src="script.js"></script>
</body>
</html>
body {
    background: #f2f2f2;
    font-family: Arial, sans-serif;
}

.container {
    width: 320px;
    margin: 80px auto;
    background: #fff;
    padding: 25px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
    text-align: center;
}

h2 {
    margin-bottom: 20px;
}

input, select {
    width: 100%;
    padding: 10px;
    margin: 8px 0;
    border-radius: 5px;
    border: 1px solid #ccc;
}

button {
    width: 100%;
    padding: 12px;
    background: #e40000;
    color: white;
    border: none;
    border-radius: 5px;
    font-size: 16px;
    cursor: pointer;
}

button:hover {
    background: #c30000;
}

#msg {
    margin-top: 15px;
    font-size: 14px;
}

body {
    background: #f1f1f1;
    font-family: Arial;
}

.box {
    width: 320px;
    background: #fff;
    margin: 80px auto;
    padding: 25px;
    text-align: center;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

input {
    width: 100%;
    padding: 10px;
    margin: 8px 0;
    border-radius: 5px;
    border: 1px solid #ccc;
}

button {
    width: 100%;
    padding: 12px;
    background: #e40000;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background: #c30000;
}

a {
    color: #e40000;
    text-decoration: none;
}

function recharge() {
    let mobile = document.getElementById("mobile").value;
    let operator = document.getElementById("operator").value;
    let amount = document.getElementById("amount").value;
    let msg = document.getElementById("msg");

    if (mobile.length !== 10 || operator === "" || amount === "") {
        msg.style.color = "red";
        msg.innerText = "Please fill all details correctly!";
    } else {
        msg.style.color = "green";
        msg.innerText = "Recharge request submitted (Demo only)";
    }
}
function signup() {
    let name = document.getElementById("name").value;
    let email = document.getElementById("email").value;
    let password = document.getElementById("password").value;
    let msg = document.getElementById("msg");

    if (name === "" || email === "" || password === "") {
        msg.style.color = "red";
        msg.innerText = "All fields are required!";
        return;
    }

    localStorage.setItem("email", email);
    localStorage.setItem("password", password);

    msg.style.color = "green";
    msg.innerText = "Signup successful! Please login.";
}

function login() {
    let email = document.getElementById("loginEmail").value;
    let password = document.getElementById("loginPassword").value;
    let msg = document.getElementById("loginMsg");

    let savedEmail = localStorage.getItem("email");
    let savedPassword = localStorage.getItem("password");

    if (email === savedEmail && password === savedPassword) {
        msg.style.color = "green";
        msg.innerText = "Login successful!";
        // window.location.href = "dashboard.html";
    } else {
        msg.style.color = "red";
        msg.innerText = "Invalid email or password!";
    }
}
