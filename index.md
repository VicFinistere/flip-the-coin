<style>
body {
  background: #fff;
  font-family: 'Ubuntu', sans-serif;
}

#coin {
   
}

#button {
  background:orange;
  color:#fff;
  padding:10px 15px;
  border-radius:2px;
  display:inline-block;
  transition:0.5s;
  cursor:pointer;
  &:hover {
    opacity:0.5;
  }
}


.animate-coin {
  animation: flip 1.4s 1;
}

@keyframes flip {
  0% {
    transform: scale3d(1,1,1) rotateX(0deg);
    box-shadow: 0 2px 4px rgba(0,0,0,.3);
  }
  50% {
    transform: scale3d(2,2,2) rotateX(3600deg);
    box-shadow: 0 20px 40px rgba(0,0,0,.8);
  }
  100% {
    transform: scale3d(1,1,1) rotateX(7200deg);
    box-shadow: 0 2px 4px rgba(0,0,0,.3);
  }
}


</style>

<script>
var coin = document.getElementById('coin');
var button = document.getElementById('button');
var result = document.getElementById('result');
var headsCounter = document.getElementById('headsCounter');
var TailsCounter = document.getElementById('TailsCounter');
var heads = 0;
var tails = 0;

/* On click of button spin coin ainamtion */
function coinToss() {
  
  /* Random number 0 or 1  */
  var x = Math.floor(Math.random() * 2);
  
  /* If statement */
  if (x === 0) {
    coin.innerHTML = '<img class="heads animate-coin" src="https://upload.wikimedia.org/wikipedia/en/5/52/British_fifty_pence_coin_2015_obverse.png"/>';
    
    heads += 1;
    result.innerHTML = 'You got heads';
    headsCounter.innerHTML = '<h1> Number of heads: ' + heads + '</h1>';

  } else {
    coin.innerHTML = '<img class="tails animate-coin" src="https://upload.wikimedia.org/wikipedia/en/d/d8/British_fifty_pence_coin_2015_reverse.png"/>';
     tails += 1;
    result.innerHTML = 'You got tails';
     tailsCounter.innerHTML = '<h1> Number of tails: ' + tails + '</h1>';

  }

}

window.onload = function(){ 
  button.onclick = function() {
    coinToss();
  } 
};
</script>


<h1>Flip the coin</h1>

<div id='coin'></div>
<div id='button'>Flip coin</div>
<div id='result'></div>
<div id='headsCounter'></div>
<div id='tailsCounter'></div>

