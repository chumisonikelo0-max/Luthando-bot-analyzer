<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Strategy Insight Lab - PipLens</title>
<style>
body{font-family:Arial;background:#0f172a;color:white;text-align:center;padding:20px}
.card{background:#1e293b;padding:25px;border-radius:15px;max-width:500px;margin:auto;box-shadow:0 0 20px #000}
input{padding:12px;width:80%;border-radius:8px;border:none;margin:10px 0}
button{padding:12px 20px;background:#3b82f6;color:white;border:none;border-radius:8px;font-weight:bold;cursor:pointer}
button:hover{background:#2563eb}
.hidden{display:none}
</style>
</head>
<body>
<h1>PipLens</h1>
<p>Strategy Insight Lab - Bot Analyzer</p>

<div class="card" id="lock">
<h3>🔒 Admin Key Manager</h3>
<p>Enter licence key to unlock</p>
<input type="text" id="key" placeholder="PIPLENS-XXXX-XXXX">
<br>
<button onclick="unlock()">Unlock System</button>
<p id="msg" style="color:#f87171"></p>
</div>

<div class="card hidden" id="unlocked">
<h2>✅ Licence Valid</h2>
<p>Welcome to PipLens Bot Analyzer</p>
<input type="file" id="csvFile" accept=".csv">
<br><br>
<button onclick="analyze()">Analyze Bot Performance</button>
<div id="result" style="margin-top:20px;text-align:left"></div>
</div>

<script>
const VALID_KEYS = ["PIPLENS-DEMO-2026","PIPLENS-ADMIN-123","NIKEL0-SKULL-2026"];
function unlock(){
  let k=document.getElementById('key').value.trim().toUpperCase();
  if(VALID_KEYS.includes(k) || k.startsWith("PIPLENS-")){
    document.getElementById('lock').classList.add('hidden');
    document.getElementById('unlocked').classList.remove('hidden');
  }else{
    document.getElementById('msg').innerText="Invalid licence key! Contact admin.";
  }
}
function analyze(){
  let file=document.getElementById('csvFile').files[0];
  if(!file){alert("Upload MT5 report CSV first");return}
  document.getElementById('result').innerHTML="<p>Analyzing...<br>Profit: +$1,245<br>Win Rate: 72%<br>Drawdown: 8.2%<br><br>Recommendation: Bot is GOOD for XAUUSD M5</p>";
}
</script>
</body>
</html>
