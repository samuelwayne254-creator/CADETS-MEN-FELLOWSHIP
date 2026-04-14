# MEN-S-FELLOWSHIP-.KE.IO 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Cadets Men Fellowship</title>

<!-- GOOGLE FONT -->
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
}

body {
    background: #0f172a;
    color: #fff;
}

/* NAVBAR */
header {
    display: flex;
    justify-content: space-between;
    padding: 15px 8%;
    position: fixed;
    width: 100%;
    background: rgba(255,255,255,0.05);
    backdrop-filter: blur(10px);
}

nav a {
    margin-left: 20px;
    text-decoration: none;
    color: #fff;
    font-size: 14px;
}

/* HERO */
.hero {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 20px;
    background: linear-gradient(135deg, #0f172a, #1e293b);
}

.hero h2 {
    font-size: 40px;
}

.hero p {
    margin: 15px 0;
    opacity: 0.8;
}

.btn {
    background: #f97316;
    border: none;
    padding: 12px 25px;
    border-radius: 8px;
    color: white;
    cursor: pointer;
}

/* CARDS */
.features {
    padding: 80px 20px;
    text-align: center;
}

.feature-box {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px,1fr));
    gap: 20px;
    margin-top: 30px;
}

.card {
    background: rgba(255,255,255,0.05);
    padding: 30px;
    border-radius: 12px;
    backdrop-filter: blur(10px);
    transition: 0.3s;
}

.card:hover {
    transform: translateY(-10px);
}

/* FORM */
.signup {
    padding: 80px 20px;
    text-align: center;
}

form {
    max-width: 400px;
    margin: auto;
    display: flex;
    flex-direction: column;
}

input {
    margin: 10px 0;
    padding: 12px;
    border-radius: 8px;
    border: none;
}

#successMsg {
    display: none;
    color: #22c55e;
}

/* WHATSAPP */
.whatsapp-btn {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background: #25D366;
    padding: 15px;
    border-radius: 50%;
    text-decoration: none;
}

/* FOOTER */
footer {
    text-align: center;
    padding: 20px;
    background: #020617;
}

/* MOBILE */
@media(max-width:768px){
    .hero h2 {font-size: 26px;}
}
</style>
</head>

<body>

<header>
    <h3>Cadets</h3>
    <nav>
        <a href="#">Home</a>
        <a href="#features">Mission</a>
        <a href="#signup">Join</a>
    </nav>
</header>

<section class="hero">
    <div>
        <h2>Building Strong Men of Purpose</h2>
        <p>Faith • Discipline • Brotherhood</p>
        <button class="btn">Join Us</button>
    </div>
</section>

<section class="features" id="features">
    <h3>Our Mission</h3>
    <div class="feature-box">
        <div class="card">Brotherhood</div>
        <div class="card">Discipline</div>
        <div class="card">Faith</div>
    </div>
</section>

<section class="signup" id="signup">
    <h3>Join Us</h3>

    <form id="signupForm">
        <input type="text" id="name" placeholder="Full Name" required>
        <input type="email" id="email" placeholder="Email" required>
        <input type="tel" id="phone" placeholder="Phone" required>
        <button class="btn">Sign Up</button>
    </form>

    <p id="successMsg">✅ Successfully joined!</p>
</section>

<section class="signup">
    <h3>Member Login</h3>

    <form id="loginForm">
        <input type="email" id="loginEmail" placeholder="Email">
        <input type="password" id="loginPassword" placeholder="Password">
        <button class="btn">Login</button>
    </form>

    <p id="loginMsg"></p>
</section>

<footer>
    <p>© 2026 Cadets Men Fellowship</p>
</footer>

<a href="https://wa.me/254782141192" class="whatsapp-btn">💬</a>

<script>
// SIGNUP → GOOGLE SHEETS
document.getElementById("signupForm").addEventListener("submit", async function(e) {
    e.preventDefault();

    let name = document.getElementById("name").value;
    let email = document.getElementById("email").value;
    let phone = document.getElementById("phone").value;

    try {
        await fetch("YOUR_GOOGLE_SCRIPT_URL_HERE", {
            method: "POST",
            body: JSON.stringify({ name, email, phone })
        });

        document.getElementById("successMsg").style.display = "block";
        signupForm.reset();

    } catch {
        alert("Error submitting form");
    }
});

// LOGIN DEMO
document.getElementById("loginForm").addEventListener("submit", function(e) {
    e.preventDefault();

    let email = document.getElementById("loginEmail").value;
    let password = document.getElementById("loginPassword").value;

    let msg = document.getElementById("loginMsg");

    if (email === "admin@cadets.com" && password === "1234") {
        msg.innerText = "Login successful";
        msg.style.color = "lightgreen";
    } else {
        msg.innerText = "Invalid login";
        msg.style.color = "red";
    }
});
</script>

</body>
</html>
