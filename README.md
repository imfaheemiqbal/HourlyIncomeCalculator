# Hourly Income Calculator
A simple hourly income calculator that estimates weekly, monthly, and yearly earnings based on hourly rate and work hours per week.
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hourly Income Calculator</title>

<style>
:root{
    --bg:#ffffff;
    --card:#f5f5f5;
    --text:#222;
    --accent:#007bff;
}

.dark{
    --bg:#121212;
    --card:#1e1e1e;
    --text:#ffffff;
    --accent:#4da3ff;
}

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    font-family:Arial, sans-serif;
    background:var(--bg);
    color:var(--text);
    transition:.3s;
    padding:20px;
}

.container{
    max-width:500px;
    margin:auto;
}

h1{
    text-align:center;
    margin-bottom:20px;
}

.card{
    background:var(--card);
    padding:20px;
    border-radius:12px;
    margin-bottom:15px;
}

label{
    display:block;
    margin-bottom:5px;
    font-weight:bold;
}

input{
    width:100%;
    padding:12px;
    border-radius:8px;
    border:1px solid #ccc;
    font-size:16px;
    margin-bottom:15px;
}

.result{
    font-size:20px;
    padding:15px;
    margin-top:10px;
    border-radius:8px;
    background:rgba(0,123,255,.1);
}

.toggle-btn{
    width:100%;
    padding:12px;
    border:none;
    border-radius:8px;
    background:var(--accent);
    color:white;
    cursor:pointer;
    font-size:16px;
    margin-bottom:15px;
}

.small{
    font-size:14px;
    opacity:.8;
}
</style>
</head>

<body>

<div class="container">

<h1>?? Hourly Income Calculator</h1>

<button class="toggle-btn" onclick="toggleTheme()">
?? Dark / ?? Light Mode
</button>

<div class="card">

<label>Hourly Rate ($)</label>
<input
type="number"
id="rate"
placeholder="e.g. 20"
oninput="calculate()">

<label>Hours Per Week</label>
<input
type="number"
id="hours"
value="40"
oninput="calculate()">

<div class="result">
Weekly Income:
<strong>$<span id="weekly">0</span></strong>
</div>

<div class="result">
Monthly Income:
<strong>$<span id="monthly">0</span></strong>
</div>

<div class="result">
Yearly Income:
<strong>$<span id="yearly">0</span></strong>
</div>

<p class="small">
Monthly = Weekly × 4<br>
Yearly = Weekly × 52
</p>

</div>

</div>

<script>

function calculate(){

let rate =
parseFloat(document.getElementById('rate').value) || 0;

let hours =
parseFloat(document.getElementById('hours').value) || 0;

let weekly = rate * hours;
let monthly = weekly * 4;
let yearly = weekly * 52;

document.getElementById('weekly').innerText =
weekly.toLocaleString();

document.getElementById('monthly').innerText =
monthly.toLocaleString();

document.getElementById('yearly').innerText =
yearly.toLocaleString();
}

function toggleTheme(){
document.body.classList.toggle('dark');
}

calculate();

</script>

</body>
</html>
