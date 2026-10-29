<!DOCTYPE html>
<html>
<head>
<title>XSS-Lab-v2 - Keeper P2 Lab $2500</title>
<style>
body{background:#000;color:#0f0;font-family:monospace;padding:20px}
input,textarea{width:100%;background:#111;color:#0f0;border:1px solid #0f0;padding:10px;margin:5px 0}
button{background:red;color:white;padding:10px;border:none;cursor:pointer}
#vault{margin-top:20px;border-top:1px solid #0f0;padding-top:10px}
.item{background:#111;padding:10px;margin:10px 0;border:1px solid #333}
</style>
</head>
<body>
<h3>🔓 XSS-Lab-v2 - Keeper P2 Lab $2500</h3>
<p>Shared Folder Name -> Stored XSS -> Anyone</p>
<input id="title" placeholder="Title / Shared Folder Name">
<textarea id="notes" placeholder="Notes"></textarea>
<button onclick="save()">SAVE - Share to Anyone</button>
<div id="vault"></div>

<script>
let items = [];
function save(){
  let t = document.getElementById('title').value;
  let n = document.getElementById('notes').value;
  items.push({title:t, notes:n});
  render();
}
function render(){
  let v = document.getElementById('vault');
  v.innerHTML = "";
  items.forEach(i=>{
    v.innerHTML += `<div class="item"><b>${i.title}</b><br>${i.notes}<br><small>To Trigger</small></div>`;
  });
}
</script>
</body>
</html>
