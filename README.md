<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SmartHub App</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f9;
            color: #333;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 10px 0;
            text-align: center;
        }
        nav {
            margin: 20px 0;
            text-align: center;
        }
        nav button {
            background-color: #4CAF50;
            border: none;
            color: white;
            padding: 10px 20px;
            margin: 5px;
            cursor: pointer;
            border-radius: 5px;
            transition: background-color 0.3s;
        }
        nav button:hover {
            background-color: #45a049;
        }
        main {
            padding: 20px;
            max-width: 600px;
            margin: auto;
        }
        section {
            background-color: white;
            padding: 20px;
            margin: 20px 0;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        form {
            display: flex;
            flex-direction: column;
        }
        form label {
            margin-bottom: 5px;
        }
        form input {
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        form button {
            background-color: #4CAF50;
            border: none;
            color: white;
            padding: 10px;
            cursor: pointer;
            border-radius: 5px;
            transition: background-color 0.3s;
        }
        form button:hover {
            background-color: #45a049;
        }
        .feedback {
            color: red;
            margin-top: 10px;
        }
        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to SmartHub</h1>
        <nav>
            <button onclick="toggleSection('sign-in')">Sign In</button>
        </nav>
    </header>
    <main>
        <section id="sign-in" class="hidden">
            <h2>Sign In</h2>
            <form id="signInForm">
                <label for="signInEmail">Email:</label>
                <input type="email" id="signInEmail" name="email" required>
                <label for="signInPassword">Password:</label>
                <input type="password" id="signInPassword" name="password" required>
                <button type="submit">Sign In</button>
                <div id="signInFeedback" class="feedback hidden"></div>
            </form>
        </section>
        <section id="access-message">
            <h2>Access Restricted</h2>
            <p>You have to sign in to access the site.</p>
        </section>
        <section id="home" class="hidden">
            <h2>Home</h2>
            <p>Welcome to the home page!</p>
        </section>
        <section id="about" class="hidden">
            <h2>About</h2>
            <p>About the page content goes here.</p>
        </section>
        <section id="profile" class="hidden">
            <h2>Profile</h2>
            <p>Profile content goes here.</p>
        </section>
        <section id="contact" class="hidden">
            <h2>Contact</h2>
            <p>Contact content goes here.</p>
        </section>
        <section id="service" class="hidden">
            <h2>Service</h2>
            <p>Service content goes here.</p>
        </section>
        <section id="feedback" class="hidden">
            <h2>Feedback</h2>
            <p>Feedback content goes here.</p>
        </section>
    </main>
    <footer>
        <p>&copy; 2023 SmartHub. All rights reserved.</p>
    </footer>
    <script>
        // Set sample sign-in details
        localStorage.setItem('email', 'khanishka@anurag.edu.in');
        localStorage.setItem('password', '12345');

        function toggleSection(sectionId) {
            const sections = document.querySelectorAll('main > section');
            sections.forEach(section => section.classList.add('hidden'));
            document.getElementById(sectionId).classList.remove('hidden');
            document.getElementById(sectionId).scrollIntoView();
        }

        document.getElementById('signInForm').addEventListener('submit', function(event) {
            event.preventDefault();
            const email = document.getElementById('signInEmail').value;
            const password = document.getElementById('signInPassword').value;
            // Simulate sign-in process
            const storedEmail = localStorage.getItem('email');
            const storedPassword = localStorage.getItem('password');
            if (email === storedEmail && password === storedPassword) {
                document.getElementById('signInFeedback').textContent = 'Sign in successful!';
                document.getElementById('signInFeedback').classList.remove('hidden');
                document.getElementById('access-message').classList.add('hidden');
                toggleSection('home');
                document.querySelector('nav').innerHTML = `
                    <button onclick="toggleSection('home')">Home</button>
                    <button onclick="toggleSection('about')">About</button>
                    <button onclick="toggleSection('profile')">Profile</button>
                    <button onclick="toggleSection('contact')">Contact</button>
                    <button onclick="toggleSection('service')">Service</button>
                    <button onclick="toggleSection('feedback')">Feedback</button>
                `;
            } else {
                document.getElementById('signInFeedback').textContent = 'Invalid email or password.';
                document.getElementById('signInFeedback').classList.remove('hidden');
            }
        });
    </script>
</body>
</html>
