<!DOCTYPE html>
<html lang="en">
<head>
  <link rel="manifest" href="manifest.json">
  <script>
    if ('serviceWorker' in navigator) {
        navigator.serviceWorker.register('/service-worker.js')
            .then(() => console.log('Service Worker Registered'));
    }
</script>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Burgeon Enterprises - Your Trusted ISP Partner</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 0; padding: 0; background-color: #eef2f7; }
        header { background: #002147; color: white; padding: 1.5rem; text-align: center; font-size: 1.5rem; }
        nav { display: flex; justify-content: center; background: #0047ab; padding: 1rem; }
        nav a { color: white; margin: 0 20px; text-decoration: none; font-weight: bold; cursor: pointer; }
        .container { padding: 40px; text-align: center; }
        .card { display: none; background: white; padding: 30px; margin: 20px auto; border-radius: 10px; max-width: 800px; box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1); }
        .active { display: block; }
        footer { background: #002147; color: white; text-align: center; padding: 1.5rem; position: relative; width: 100%; margin-top: 40px; }
        button { background: #0047ab; color: white; border: none; padding: 10px 20px; border-radius: 5px; font-size: 1rem; cursor: pointer; }
        button:hover { background: #002147; }
        input { padding: 10px; margin: 5px; width: 80%; border: 1px solid #ccc; border-radius: 5px; }
    </style>
    <script>
        function showSection(sectionId) {
            document.querySelectorAll('.card').forEach(card => card.classList.remove('active'));
            document.getElementById(sectionId).classList.add('active');
        }
        
        function handleLogin() {
            let email = document.getElementById('email').value;
            let password = document.getElementById('password').value;
            if(email && password) {
                alert('Login successful for ' + email);
            } else {
                alert('Please enter both email and password');
            }
        }
        
        function runSpeedTest() {
            let startTime = new Date().getTime();
            let download = new Image();
            download.onload = function() {
                let endTime = new Date().getTime();
                let duration = (endTime - startTime) / 1000;
                let bitsLoaded = 8 * 1024 * 1024;
                let speedMbps = (bitsLoaded / duration / 1024 / 1024).toFixed(2);
                alert('Your estimated internet speed: ' + speedMbps + ' Mbps');
            };
            download.src = "https://via.placeholder.com/1024x1024.jpg?" + new Date().getTime();
        }
    </script>
</head>
<body>
    <header>
        <h1>Burgeon Enterprises</h1>
    </header>
    <nav>
        <a onclick="showSection('about')">About Us</a>
        <a onclick="showSection('services')">Services</a>
        <a onclick="showSection('contact')">Contact</a>
        <a onclick="showSection('partner')">Partner with Us</a>
        <a onclick="showSection('account')">Client Portal</a>
        <a onclick="showSection('speedtest')">Speed Test</a>
    </nav>
    <div class="container">
        <div class="card active" id="about">
            <h2>About Us</h2>
            <p>At Burgeon Enterprises, we specialize in high-speed internet solutions, network infrastructure, and IT services to ensure reliable and seamless connectivity for homes and businesses.</p>
        </div>
        <div class="card" id="services">
            <h2>Our Services</h2>
            <ul>
                <li>High-Speed Internet Installation & Maintenance</li>
                <li>Enterprise Networking Solutions</li>
                <li>Retail & Sale of IT Equipment</li>
                <li>Cloud Computing & Security Solutions</li>
            </ul>
            <button>Learn More</button>
        </div>
        <div class="card" id="contact">
            <h2>Contact Us</h2>
            <p>Phone: 0915-656-4278</p>
            <p>Email: burgeonenterprises2020@gmail.com</p>
            <p>Address: Turquoise St. The Cambria Bay, Bay, Laguna</p>
            <button>Get in Touch</button>
        </div>
        <div class="card" id="partner">
            <h2>Partner with Us</h2>
            <p>We are looking to collaborate with trusted internet service providers to enhance connectivity for our clients. If interested, let's work together!</p>
            <button>Partner Now</button>
        </div>
        <div class="card" id="account">
            <h2>Client Portal</h2>
            <p>Access your account, check your internet plan, and manage your billing information.</p>
            <input type="email" id="email" placeholder="Enter your email" required><br>
            <input type="password" id="password" placeholder="Enter your password" required><br>
            <button onclick="handleLogin()">Login</button>
            <button>Register</button>
        </div>
        <div class="card" id="speedtest">
            <h2>Internet Speed Test</h2>
            <p>Click the button below to test your internet speed.</p>
            <button onclick="runSpeedTest()">Run Speed Test</button>
        </div>
    </div>
    <footer>
        <p>&copy; 2024 Burgeon Enterprises. All rights reserved.</p>
    </footer>
</body>
</html>
# burgeon-website
Burgeon Enterprises Website
