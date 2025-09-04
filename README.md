# _FRIENDCHECK_

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fake or Real Friend Wall 🎲</title>
<style>
    body {
        font-family: 'Arial', sans-serif;
        background: linear-gradient(135deg, #fceabb, #f8b500);
        text-align: center;
        padding: 20px;
    }
    h1 {
        color: #ff4b5c;
        margin-bottom: 30px;
    }
    input {
        padding: 10px;
        width: 250px;
        margin: 10px 0;
        border-radius: 8px;
        border: 1px solid #ccc;
        font-size: 16px;
    }
    button {
        padding: 10px 20px;
        border: none;
        border-radius: 8px;
        background-color: #ff4b5c;
        color: white;
        font-size: 16px;
        cursor: pointer;
        margin-left: 10px;
    }
    button:hover {
        background-color: #ff2e3c;
    }
    #resultWall {
        max-width: 600px;
        margin: 30px auto 0;
        text-align: left;
    }
    .result {
        background: #fff;
        padding: 10px 15px;
        margin: 10px 0;
        border-radius: 10px;
        box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        font-size: 18px;
    }
    .real {
        color: green;
        font-weight: bold;
    }
    .fake {
        color: red;
        font-weight: bold;
    }
</style>
</head>
<body>

<h1>Fake or Real Friend Wall 🎲</h1>

<input type="text" id="friendName" placeholder="Enter friend's name">
<button onclick="checkFriend()">Check</button>

<div id="resultWall">
    <!-- All results appear here -->
</div>

<script>
function checkFriend() {
    const nameInput = document.getElementById('friendName');
    const name = nameInput.value.trim();
    if(name === ""){
        alert("Please enter a friend's name!");
        return;
    }

    // Randomly decide Fake or Real
    const isReal = Math.random() < 0.5;
    const outcome = isReal ? "Real Friend 😎" : "Fake Friend 😂";

    // Create result div
    const resultDiv = document.createElement('div');
    resultDiv.classList.add('result');
    resultDiv.innerHTML = `<strong>${name}:</strong> <span class="${isReal ? 'real' : 'fake'}">${outcome}</span>`;

    // Add to wall on top
    const wall = document.getElementById('resultWall');
    wall.prepend(resultDiv);

    // Clear input
    nameInput.value = "";
}
</script>

</body>
</html>
