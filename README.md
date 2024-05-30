<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UI Members Site</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(120deg, #2980b9, #8e44ad);
            color: #fff;
            text-align: center;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            background: rgba(0, 0, 0, 0.5);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
        }

        .title {
            font-size: 2.5em;
            font-weight: bold;
            color: metallic;
            text-shadow: 0 0 5px rgba(0, 0, 0, 0.5);
        }

        .description {
            font-size: 1.2em;
            margin: 20px 0;
        }

        .buttons button {
            font-size: 1em;
            padding: 10px 20px;
            margin: 10px;
            border: none;
            border-radius: 5px;
            background: #3498db;
            color: #fff;
            cursor: pointer;
            transition: background 0.3s;
        }

        .buttons button:hover {
            background: #2980b9;
        }

        footer {
            margin-top: 30px;
        }

        footer em {
            font-style: italic;
            color: #ecf0f1;
        }
        
        #errorMessage, #adminErrorMessage {
            display: none;
            color: red;
        }

        #mediaContent, #adminContent {
            display: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 class="title">UI Members Site</h1>
        <p class="description">
            This website is entirely dedicated to the UI members and has some other important photos.
            If you are an RSN student or its relative then you can access the media of this website.
        </p>
        <div class="buttons">
            <button onclick="showMediax()">Mediax</button>
            <button onclick="showAdminx()">Adminx</button>
        </div>
        <footer>
            <p><em>Created by lord primus</em></p>
        </footer>
    </div>

    <div class="container" id="mediax" style="display: none;">
        <h1 class="title">Mediax</h1>
        <form id="passwordForm" onsubmit="return checkPassword()">
            <input type="password" id="password" placeholder="Enter password">
            <button type="submit">Submit</button>
        </form>
        <div id="errorMessage">Invalid password</div>
        <div id="mediaContent">
            <h2>Photos</h2>
            <div id="photos">
                <!-- Photos will be displayed here -->
                <img src="https://via.placeholder.com/150" alt="Photo 1">
                <img src="https://via.placeholder.com/150" alt="Photo 2">
                <img src="https://via.placeholder.com/150" alt="Photo 3">
            </div>
        </div>
    </div>

    <div class="container" id="adminx" style="display: none;">
        <h1 class="title">Adminx</h1>
        <form id="adminPasswordForm" onsubmit="return checkAdminPassword()">
            <input type="password" id="adminPassword" placeholder="Enter password">
            <button type="submit">Submit</button>
        </form>
        <div id="adminErrorMessage">Invalid password</div>
        <div id="adminContent">
            <h2>Manage Photos</h2>
            <form id="uploadForm" enctype="multipart/form-data" method="post" action="#">
                <input type="file" name="photo" id="photo">
                <button type="submit">Upload Photo</button>
            </form>
            <div id="photoGallery">
                <!-- Uploaded photos will be displayed here -->
                <img src="https://via.placeholder.com/150" alt="Photo 1">
                <img src="https://via.placeholder.com/150" alt="Photo 2">
            </div>
        </div>
    </div>

    <script>
        function showMediax() {
            document.querySelector('.container').style.display = 'none';
            document.getElementById('mediax').style.display = 'block';
        }

        function showAdminx() {
            document.querySelector('.container').style.display = 'none';
            document.getElementById('adminx').style.display = 'block';
        }

        function checkPassword() {
            var password = document.getElementById("password").value;
            if (password === "7998") {
                document.getElementById("errorMessage").style.display = "none";
                document.getElementById("mediaContent").style.display = "block";
            } else {
                document.getElementById("errorMessage").style.display = "block";
            }
            return false;
        }

        function checkAdminPassword() {
            var password = document.getElementById("adminPassword").value;
            if (password === "3697") {
                document.getElementById("adminErrorMessage").style.display = "none";
                document.getElementById("adminContent").style.display = "block";
            } else {
                document.getElementById("adminErrorMessage").style.display = "block";
            }
            return false;
        }
    </script>
</body>
</html>