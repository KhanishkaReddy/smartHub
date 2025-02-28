# smartHub
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SmartHub App</title>
    <link rel="stylesheet" href="styles.css">
    <style>
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
            <button onclick="toggleSection('sign-up')">Sign Up</button>
        </nav>
    </header>
    <main>
        <section id="dashboard">
            <h2>Dashboard</h2>
            <!-- Dashboard content goes here -->
        </section>
        <section id="settings">
            <h2>Settings</h2>
            <!-- Settings content goes here -->
        </section>
        <section id="sign-in" class="hidden">
            <h2>Sign In</h2>
            <form id="signInForm">
                <label for="signInEmail">Email:</label>
                <input type="email" id="signInEmail" name="email" required>
                <label for="signInPassword">Password:</label>
                <input type="password" id="signInPassword" name="password" required>
                <button type="submit">Sign In</button>
            </form>
        </section>
        <section id="sign-up" class="hidden">
            <h2>Sign Up</h2>
            <form id="signUpForm">
                <label for="signUpEmail">Email:</label>
                <input type="email" id="signUpEmail" name="email" required>
                <label for="signUpPassword">Password:</label>
                <input type="password" id="signUpPassword" name="password" required>
                <label for="signUpConfirmPassword">Confirm Password:</label>
                <input type="password" id="signUpConfirmPassword" name="confirmPassword" required>
                <button type="submit">Sign Up</button>
            </form>
        </section>
    </main>
    <footer>
        <p>&copy; 2023 SmartHub. All rights reserved.</p>
    </footer>
    <script>
        function toggleSection(sectionId) {
            document.getElementById('sign-in').classList.add('hidden');
            document.getElementById('sign-up').classList.add('hidden');
            document.getElementById(sectionId).classList.remove('hidden');
            document.getElementById(sectionId).scrollIntoView();
        }
    </script>
</body>
</html>
