# music
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>Music App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f2f2f2;
        }
        .login-container {
            width: 300px;
            margin: 100px auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        h2 {
            text-align: center;
        }
        input[type="text"], input[type="password"] {
            width: 100%;
            padding: 10px;
            margin: 8px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        button {
            width: 100%;
            padding: 10px;
            margin-top: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
        .control-panel {
            display: none;
            padding: 20px;
        }
        #songList {
            list-style-type: none;
            padding: 0;
        }
        #songList li {
            padding: 8px;
            background-color: #e2e2e2;
            margin-bottom: 4px;
            border-radius: 4px;
        }
    </style>
</head>
<body>

<div class="login-container" id="loginDiv">
    <h2>Login</h2>
    <input type="text" id="username" placeholder="Username" required />
    <input type="password" id="password" placeholder="Password" required />
    <button onclick="login()">Login</button>
</div>

<div class="control-panel" id="appDiv">
    <h2>Music Control Panel</h2>
    <input type="text" id="songInput" placeholder="Enter song name" />
    <button onclick="addSong()">Add Song</button>
    <h3>Song List:</h3>
    <ul id="songList"></ul>
</div>

<script>
    function login() {
        // Simple login validation (can be replaced with real auth)
        const username = document.getElementById('username').value;
        const password = document.getElementById('password').value;
        if(username && password) {
            document.getElementById('loginDiv').style.display = 'none';
            document.getElementById('appDiv').style.display = 'block';
        } else {
            alert('Please enter username and password.');
        }
    }

    function addSong() {
        const songName = document.getElementById('songInput').value;
        if(songName.trim() !== "") {
            const li = document.createElement('li');
            li.textContent = songName;
            document.getElementById('songList').appendChild(li);
            document.getElementById('songInput').value = '';
        } else {
            alert('Please enter a song name.');
        }
    }
</script>

</body>
</html>
