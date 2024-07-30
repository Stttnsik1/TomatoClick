<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<link rel="stylesheet" href="style.css">
</head>
<center><strong><h1><span id="score">0</span></h1></strong></center>
<center><h3><span id="gems">0</span>💎</h3></center>

<center><button class="tomat" id="myButton" onclick="earntomato()"><img src="https://i.postimg.cc/05Jd47rK/2687984-B-2-A93-4-D5-C-8-A0-F-ED2535041340.png" width="450px" height="450px"></button></center>

<center><div class="circle">
<form action="Market.html">
<center><button class="market"><img class="tomatoimg" src="https://i.postimg.cc/bJ8Hn6vM/6232458.png" width="55px" height="55px"></button></center>
</form>
</div></center>
</html>


<script>
let score = 0;
 let clickValue = 1;
 let wateringsBought = 0;

 window.onload = function() {
  let savedScore = localStorage.getItem('score');
  if (savedScore) {
    score = parseInt(savedScore);
    document.getElementById('score').textContent = score;
  }

  let savedGems = localStorage.getItem('gems'); // Correct ID for local storage
      if (savedGems) {
        gems = parseInt(savedGems);
        document.getElementById('gems').textContent = gems; // Update gems display
      }
};

 function earntomato() {
   score += clickValue;
   document.getElementById('score').textContent = score;
   localStorage.setItem('score', score);
 }
 const button = document.getElementById('myButton');

    button.addEventListener(' ', function(event) {
      // Prevent default keypress behavior for spacebar and Enter
      if (event.key === ' ' || event.key === ' ') {
        event.preventDefault(); 
      }
    });

    button.addEventListener('click', function() {
      console.log('Button clicked by mouse!'); 
    });

    function Buy() {
      let cost = 10 * Math.pow(2, wateringsBought); 
      if (score >= cost) {
        score -= cost;
        clickValue *= 2;
        wateringsBought++;
        document.getElementById('score').textContent = score;
        document.getElementById('clickValue').textContent = clickValue; // Display clickValue
        document.getElementById('wateringsBought').textContent = wateringsBought; // Display wateringsBought
        localStorage.setItem('clickValue', clickValue);
        localStorage.setItem('wateringsBought', wateringsBought);
        localStorage.setItem('score', score);
      } else {
        alert('Недостаточно очков для покупки полива!');
      }
    }
</script>
