<style>
body {
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
  border-radius:50%;
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

/* Au clic sur le bouton on lance l'animation */
function coinToss() {
  
  var coin = document.getElementById('coin');
  var result = document.getElementById('result');
  
  /* Nombre aléatoire entre 0 et 1  */
  var x = Math.floor(Math.random() * 2);
  
  /* Si c'est 0 ou si c'est 1 */
  if (x === 0) {
    coin.innerHTML = '<img class="heads animate-coin" src="https://upload.wikimedia.org/wikipedia/en/5/52/British_fifty_pence_coin_2015_obverse.png"/>';
    
    result.innerHTML = "<p>C'est face !</p>";
  } else {
    coin.innerHTML = '<img class="tails animate-coin" src="https://upload.wikimedia.org/wikipedia/en/d/d8/British_fifty_pence_coin_2015_reverse.png"/>';
    result.innerHTML = "<p>C'est pile !</p>";
  }

}
</script>


<h1>Tirer à pile ou face</h1>

<div id='coin'></div>
<div id='result'></div>
<div id='button' onclick="coinToss()">Flip coin</div>

