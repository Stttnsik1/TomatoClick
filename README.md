<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<link rel="stylesheet" href="style.css">
</head>
<h1><span id="score">0</span></h1>
<center><button onclick="earntomato()"><img src="https://i.postimg.cc/05Jd47rK/2687984-B-2-A93-4-D5-C-8-A0-F-ED2535041340.png" width="450px" height="450px"></button></center>
</html>
<script>
 let score = 0;
 let clickValue = 1;
 let wateringsBought = 0;

 function earntomato() {
   score += clickValue;
   document.getElementById('score').textContent = score;
 }
</script>
