<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quantumbots Trader</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: black;
            background-image: url('https://www.shutterstock.com/image-photo/rise-glow-arrow-volatility-index-600nw-2416940383.jpg');
            background-repeat: no-repeat;
            background-position: center;
            background-size: cover;
            color: white;
            box-sizing: border-box;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
        }
        header {
            width: 100%;
            background-color: rgba(0, 0, 139, 0.9);
            color: white;
            padding: 20px 0;
            position: fixed;
            top: 0;
            left: 0;
            z-index: 1000;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3);
        }
        header h1 {
            margin: 0;
            font-size: 2rem;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.7);
        }
        main {
            padding-top: 130px;
            text-align: center;
            flex: 1;
            width: 100%;
        }
        .main-title {
            font-size: 1.4rem;
            font-weight: bold;
            margin: 20px 0;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.7);
        }
        .sub-title {
            font-size: 1.2rem;
            margin: 10px 0;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.7);
        }
        .get-started-btn {
            background-color: white;
            color: #00008B;
            border: 2px solid #00008B;
            padding: 10px 20px;
            font-size: 1.2rem;
            font-weight: bold;
            text-decoration: none;
            border-radius: 5px;
            display: inline-block;
            margin-top: 20px;
            cursor: pointer;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
        }
        .get-started-btn:hover {
            background-color: #00008B;
            color: white;
        }
        .registration-form {
            display: none;
            margin-top: 50px;
            text-align: left;
            background-color: rgba(255, 255, 255, 0.8);
            padding: 20px;
            border-radius: 8px;
            width: 90%;
            max-width: 400px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
            margin-bottom: 20px;
        }
        .registration-form input,
        .registration-form select,
        .registration-form button {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .registration-form button {
            background-color: #00008B;
            color: white;
            border: none;
            font-weight: bold;
            cursor: pointer;
        }
        .registration-form button:hover {
            background-color: #333;
        }
        .terms {
            font-size: 0.75rem;
            text-align: center;
            margin-top: 10px;
            color: #888;
        }
        .loading {
            display: none;
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 1.5rem;
            color: white;
            background-color: rgba(0, 0, 0, 0.7);
            padding: 20px 40px;
            border-radius: 10px;
            z-index: 1001;
        }
        .loading .spinner {
            border: 8px solid #f3f3f3;
            border-top: 8px solid #00008B;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        .new-interface {
            display: none;
            background-color: white;
            width: 100%;
            height: 100%;
            position: fixed;
            top: 0;
            left: 0;
            z-index: 1000;
            padding: 20px;
            box-sizing: border-box;
            text-align: center;
        }
        .new-interface h1 {
            font-size: 2rem;
            font-weight: bold;
            color: white;
            background-color: #00008B;
            padding: 10px 20px;
            border-radius: 8px;
            text-shadow: none;
        }
        .new-interface p {
            font-size: 1rem;
            color: #555;
        }
        .propfirm-plan-form {
            margin-top: 20px;
            text-align: left;
            display: inline-block;
            background-color: skyblue;
            padding: 20px;
            border-radius: 8px;
            width: 100%;
            max-width: 500px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
            box-sizing: border-box;
        }
        .propfirm-plan-form h3 {
            font-size: 1.4rem;
            font-weight: bold;
            margin-bottom: 20px;
            color: #333;
        }
        .propfirm-plan-form input[type="radio"] {
            margin-right: 10px;
        }
        .propfirm-plan-form label {
            font-size: 1.1rem;
            display: block;
            margin-bottom: 15px;
            color: #333;
            padding: 5px 0;
        }
        .submit-btn {
            background-color: #00008B;
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 1.2rem;
            font-weight: bold;
            cursor: pointer;
            border-radius: 5px;
            width: 100%;
        }
        .submit-btn:hover {
            background-color: #333;
        }
        html {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body>
    <header>
        <h1>QUANTUMBOTS TRADER</h1>
    </header>
    <main>
        <p class="main-title">
            GET A PROPFIRM WITHOUT CHALLENGE AND START MAKING WITHDRAWABLE PROFITS ON THE GO 🚀
        </p>
        <p class="sub-title">
            Join over 750,000 traders in the world’s leading firm. Trade in a fully simulated environment and earn up to 100% rewards.
        </p>
        <a href="#registrationForm" class="get-started-btn" id="getStartedBtn">Get Started</a>

        <!-- Registration Form -->
        <div class="registration-form" id="registrationForm">
            <h2>Register Now</h2>
            <form id="form">
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" required>

                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>

                <label for="age">Age:</label>
                <input type="number" id="age" name="age" min="15" required>

                <label for="experience">Trading Experience:</label>
                <select id="experience" name="experience" required>
                    <option value="beginner">Beginner</option>
                    <option value="intermediate">Intermediate</option>
                    <option value="expert">Expert</option>
                </select>

                <label for="phone">Phone Number:</label>
                <input type="tel" id="phone" name="phone" required>

                <button type="submit">REGISTER NOW</button>
            </form>
            <p class="terms">
                By registering, you agree with our <a href="#" style="color: #00008B; text-decoration: underline;">terms and conditions</a>.
            </p>
        </div>

        <!-- Loading Animation -->
        <div class="loading" id="loading">
            <div class="spinner"></div>
            Please wait...
        </div>

        <!-- New Interface -->
        <div class="new-interface" id="newInterface">
            <h1 id="userName">WELCOME</h1>
            <p id="userEmail"></p>

            <div class="propfirm-plan-form">
                <h3>SELECT PROPFIRM PLAN</h3>
                <label>
                    <input type="radio" name="plan" value="$5,000 - $73">
                    $5,000 - $73
                </label>
                <label>
                    <input type="radio" name="plan" value="$10,000 - $140">
                    $10,000 - $140
                </label>
                <label>
                    <input type="radio" name="plan" value="$20,000 - $250">
                    $20,000 - $250
                </label>
                <label>
                    <input type="radio" name="plan" value="$50,000 - $450">
                    $50,000 - $450
                </label>
                <label>
                    <input type="radio" name="plan" value="$100,000 - $750">
                    $100,000 - $750
                </label>
                <label>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quantumbots Trader</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: black;
            background-image: url('https://www.shutterstock.com/image-photo/rise-glow-arrow-volatility-index-600nw-2416940383.jpg');
            background-repeat: no-repeat;
            background-position: center;
            background-size: cover;
            color: white;
            box-sizing: border-box;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
        }
        header {
            width: 100%;
            background-color: rgba(0, 0, 139, 0.9);
            color: white;
            padding: 20px 0;
            position: fixed;
            top: 0;
            left: 0;
            z-index: 1000;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3);
        }
        header h1 {
            margin: 0;
            font-size: 2rem;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.7);
        }
        main {
            padding-top: 130px;
            text-align: center;
            flex: 1;
            width: 100%;
        }
        .main-title {
            font-size: 1.4rem;
            font-weight: bold;
            margin: 20px 0;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.7);
        }
        .sub-title {
            font-size: 1.2rem;
            margin: 10px 0;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.7);
        }
        .get-started-btn {
            background-color: white;
            color: #00008B;
            border: 2px solid #00008B;
            padding: 10px 20px;
            font-size: 1.2rem;
            font-weight: bold;
            text-decoration: none;
            border-radius: 5px;
            display: inline-block;
            margin-top: 20px;
            cursor: pointer;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
        }
        .get-started-btn:hover {
            background-color: #00008B;
            color: white;
        }
        .registration-form {
            display: none;
            margin-top: 50px;
            text-align: left;
            background-color: rgba(255, 255, 255, 0.8);
            padding: 20px;
            border-radius: 8px;
            width: 90%;
            max-width: 400px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
            margin-bottom: 20px;
        }
        .registration-form input,
        .registration-form select,
        .registration-form button {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .registration-form button {
            background-color: #00008B;
            color: white;
            border: none;
            font-weight: bold;
            cursor: pointer;
        }
        .registration-form button:hover {
            background-color: #333;
        }
        .terms {
            font-size: 0.75rem;
            text-align: center;
            margin-top: 10px;
            color: #888;
        }
        .loading {
            display: none;
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 1.5rem;
            color: white;
            background-color: rgba(0, 0, 0, 0.7);
            padding: 20px 40px;
            border-radius: 10px;
            z-index: 1001;
        }
        .loading .spinner {
            border: 8px solid #f3f3f3;
            border-top: 8px solid #00008B;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        .new-interface {
            display: none;
            background-color: white;
            width: 100%;
            height: 100%;
            position: fixed;
            top: 0;
            left: 0;
            z-index: 1000;
            padding: 20px;
            box-sizing: border-box;
            text-align: center;
        }
        .new-interface h1 {
            font-size: 2rem;
            font-weight: bold;
            color: white;
            background-color: #00008B;
            padding: 10px 20px;
            border-radius: 8px;
            text-shadow: none;
        }
        .new-interface p {
            font-size: 1rem;
            color: #555;
        }
        .propfirm-plan-form {
            margin-top: 20px;
            text-align: left;
            display: inline-block;
            background-color: skyblue;
            padding: 20px;
            border-radius: 8px;
            width: 100%;
            max-width: 500px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
            box-sizing: border-box;
        }
        .propfirm-plan-form h3 {
            font-size: 1.4rem;
            font-weight: bold;
            margin-bottom: 20px;
            color: #333;
        }
        .propfirm-plan-form input[type="radio"] {
            margin-right: 10px;
        }
        .propfirm-plan-form label {
            font-size: 1.1rem;
            display: block;
            margin-bottom: 15px;
            color: #333;
            padding: 5px 0;
        }
        .submit-btn {
            background-color: #00008B;
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 1.2rem;
            font-weight: bold;
            cursor: pointer;
            border-radius: 5px;
            width: 100%;
        }
        .submit-btn:hover {
            background-color: #333;
        }
        html {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body>
    <header>
        <h1>QUANTUMBOTS TRADER</h1>
    </header>
    <main>
        <p class="main-title">
            GET A PROPFIRM WITHOUT CHALLENGE AND START MAKING WITHDRAWABLE PROFITS ON THE GO 🚀
        </p>
        <p class="sub-title">
            Join over 750,000 traders in the world’s leading firm. Trade in a fully simulated environment and earn up to 100% rewards.
        </p>
        <a href="#registrationForm" class="get-started-btn" id="getStartedBtn">Get Started</a>

        <!-- Registration Form -->
        <div class="registration-form" id="registrationForm">
            <h2>Register Now</h2>
            <form id="form">
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" required>

                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>

                <label for="age">Age:</label>
                <input type="number" id="age" name="age" min="15" required>

                <label for="experience">Trading Experience:</label>
                <select id="experience" name="experience" required>
                    <option value="beginner">Beginner</option>
                    <option value="intermediate">Intermediate</option>
                    <option value="expert">Expert</option>
                </select>

                <label for="phone">Phone Number:</label>
                <input type="tel" id="phone" name="phone" required>

                <button type="submit">REGISTER NOW</button>
            </form>
            <p class="terms">
                By registering, you agree with our <a href="#" style="color: #00008B; text-decoration: underline;">terms and conditions</a>.
            </p>
        </div>

        <!-- Loading Animation -->
        <div class="loading" id="loading">
            <div class="spinner"></div>
            Please wait...
        </div>

        <!-- New Interface -->
        <div class="new-interface" id="newInterface">
            <h1 id="userName">WELCOME</h1>
            <p id="userEmail"></p>

            <div class="propfirm-plan-form">
                <h3>SELECT PROPFIRM PLAN</h3>
                <label>
                    <input type="radio" name="plan" value="$5,000 - $73">
                    $5,000 - $73
                </label>
                <label>
                    <input type="radio" name="plan" value="$10,000 - $140">
                    $10,000 - $140
                </label>
                <label>
                    <input type="radio" name="plan" value="$20,000 - $250">
                    $20,000 - $250
                </label>
                <label>
                    <input type="radio" name="plan" value="$50,000 - $450">
                    $50,000 - $450
                </label>
                <label>
                    <input type="radio" name="plan" value="$100,000 - $750">
                    $100,000 - $750
                </label>
                <label>
                    <input type="radio" name="plan" value="$200,000 - $1,400">
                    $200,000 - $1,400
                </label>
                <label>
                    <input type="radio" name="plan" value="$500,000 - $2,500">
                    $500,000 - $2,500
                </label>
                <label>
                    <input type="radio" name="plan" value="$1,000,000 - $4,700">
                    $1,000,000 - $4,700
                </label>
                <button class="submit-btn" id="submitBtn">Submit</button>
            </div>
        </div>
    </main>

    <script>
        document.getElementById('getStartedBtn').addEventListener('click', function() {
            document.querySelector('.registration-form').style.display = 'block';
        });

        document.getElementById('form').addEventListener('submit', function(event) {
            event.preventDefault();
            document.getElementById('loading').style.display = 'block';

            let name = document.getElementById('name').value;
            let email = document.getElementById('email').value;
            let age = document.getElementById('age').value;
            let phone = document.getElementById('phone').value;

            setTimeout(function() {
                document.getElementById('loading').style.display = 'none';
                document.getElementById('newInterface').style.display = 'block';
                document.getElementById('userName').textContent = 'WELCOME ' + name;
                document.getElementById('userEmail').textContent = email;
            }, 3000);
        });

        document.getElementById('submitBtn').addEventListener('click', function() {
            const name = document.getElementById('name').value;
            const age = document.getElementById('age').value;
            const phone = document.getElementById('phone').value;
            const email = document.getElementById('email').value;
            const plan = document.querySelector('input[name="plan"]:checked').value;

            const message = `Hi i want to purchase the QUANTUMBOT PROPFIRM ACCOUNT.\nNAME: ${name}\nAGE: ${age}\nPHONE NUMBER: ${phone}\nEMAIL: ${email}\nMY SELECTED PLAN: ${plan}`;

            const whatsappLink = `https://wa.me/+18049731977?text=${encodeURIComponent(message)}`;
            window.location.href = whatsappLink;
        });
    </script>
</body>
</html>
￼Enter                    <input type="radio" name="plan" value="$200,000 - $1,400">
                    $200,000 - $1,400
                </label>
                <label>
                    <input type="radio" name="plan" value="$500,000 - $2,500">
                    $500,000 - $2,500
                </label>
                <label>
                    <input type="radio" name="plan" value="$1,000,000 - $4,700">
                    $1,000,000 - $4,700
                </label>
                <button class="submit-btn" id="submitBtn">Submit</button>
            </div>
        </div>
    </main>

    <script>
  document.getElementById('getStartedBtn').addEventListener('click', function() {
            document.querySelector('.registration-form').style.display = 'block';
        });

        document.getElementById('form').addEventListener('submit', function(event) {
            event.preventDefault();
            document.getElementById('loading').style.display = 'block';

            let name = document.getElementById('name').value;
            let email = document.getElementById('email').value;
            let age = document.getElementById('age').value;
            let phone = document.getElementById('phone').value;

            setTimeout(function() {
                document.getElementById('loading').style.display = 'none';
                document.getElementById('newInterface').style.display = 'block';
                document.getElementById('userName').textContent = 'WELCOME ' + name;
