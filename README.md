<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Classroom App - Login</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Welcome to Classroom App</h1>
        <form id="loginForm">
            <input type="text" id="username" placeholder="Username" required>
            <input type="password" id="password" placeholder="Password" required>
            <select id="role" required>
                <option value="">Select Role</option>
                <option value="admin">Admin</option>
                <option value="student">Student</option>
            </select>
            <button type="submit">Login</button>
        </form>
    </div>

    <script>
        document.getElementById('loginForm').addEventListener('submit', function(event) {
            event.preventDefault();
            const role = document.getElementById('role').value;
            const username = document.getElementById('username').value;

            if (role) {
                localStorage.setItem('role', role);
                localStorage.setItem('username', username);
                window.location.href = `dashboard.html?role=${role}`;
            } else {
                alert('Please select a role.');
            }
        });
    </script>
</body>
</html>

