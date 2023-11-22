<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Operaciones de Conjuntos</title>
  <style>
    body {
      font-family: Arial;

  background: -moz-linear-gradient(45deg, #02e1ba 0%, #26c9f2 29%, #d911f2 66%, #ffa079 100%);
  background: -webkit-linear-gradient(45deg, #02e1ba 0%,#26c9f2 29%,#d911f2 66%,#ffa079 100%);
  background: linear-gradient(45deg, #02e1ba 0%,#26c9f2 29%,#d911f2 66%,#ffa079 100%);
  background-size: 400% 400%;
  -webkit-animation: Gradient 15s ease infinite;
  -moz-animation: Gradient 15s ease infinite;
  animation: Gradient 15s ease infinite;
  min-height: calc(100vh - 2rem);
  display: flex;
  flex-direction: column;
  align-items: stretch;
  justify-content: space-evenly;
  overflow: hidden;
  position: relative;
}

body::before,
body::after {
  content: "";
  width: 70vmax;
  height: 70vmax;
  position: absolute;
  background: rgba(255, 255, 255, 0.07);
  left: -20vmin;
  top: -20vmin;
  animation: morph 15s linear infinite alternate, spin 20s linear infinite;
  z-index: 1;
  will-change: border-radius, transform;
  transform-origin: 30% 30%;
  pointer-events: none;
}
 
body::after {
    width: 70vmin;
    height: 70vmin;
    left: auto;
    right: -10vmin;
    top: auto;
    bottom: 0;
    animation: morph 10s linear infinite alternate, spin 26s linear infinite reverse;
    transform-origin: 10% 10%;
}

@-webkit-keyframes Gradient {
  0% {
    background-position: 0 50%
  }
  50% {
    background-position: 100% 50%
  }
  100% {
    background-position: 0 50%
  }
}

@-moz-keyframes Gradient {
  0% {
    background-position: 0 50%
  }
  50% {
    background-position: 100% 50%
  }
  100% {
    background-position: 0 50%
  }
}

@keyframes Gradient {
  0% {
    background-position: 0 50%
  }
  50% {
    background-position: 100% 50%
  }
  100% {
    background-position: 0 50%
  }
}

@keyframes morph {
  0% {
    border-radius: 40% 60% 60% 40% / 70% 30% 70% 30%; }
  100% {
    border-radius: 40% 60%; }
}

@keyframes spin {
  to {
    transform: rotate(1turn);
  }
}
  .st0{display:none;}
  .st1{display:inline;}
  .st2{opacity:0.29;}
  .st3{fill:#FFFFFF;}
  .st4{clip-path:url(#SVGID_2_);fill:#FFFFFF;}
  .st5{clip-path:url(#SVGID_4_);}
  .st6{clip-path:url(#SVGID_6_);}
  .st7{clip-path:url(#SVGID_8_);}
  .st8{clip-path:url(#SVGID_10_);}
  .st9{fill:none;}
  .st10{clip-path:url(#SVGID_12_);}
  .st11{opacity:0.7;}
  .st12{clip-path:url(#SVGID_14_);}
  .st13{opacity:0.2;}
  .st14{clip-path:url(#SVGID_16_);}
  .st15{opacity:0.3;fill:#FFFFFF;enable-background:new;
   }

    input {
      font-family: Verdana,sans-serif;
      font-size: 20px;
      height: 35px;
      width: 55%;
      margin: 5px;
      background-color: white;
      border-radius: 5px;
    }

    button{
      border-radius: 5px;
      font-family: Verdana,sans-serif;
      font-size: 20px;
      height: 45px;
      width: 17%;
      margin: 5px;
      background-color: white;
    }

    div{
      font-size: 21px;
    }

    label{
      font-size: 18px;
    }

  </style>
</head>
<body>

  <h2>Operaciones de Conjuntos</h2>
  <label for="setA">Conjunto A:</label>
  <input type="text" id="setA" placeholder="Ej: 1, 2, 3">

  <label for="setB">Conjunto B:</label>
  <input type="text" id="setB" placeholder="Ej: 3, 4, 5"><br>

  <h3>Operaciones:</h3>

  <button onclick="union()">Unión</button>
  <button onclick="interseccion()">Intersección</button>
  <button onclick="diferencia()">Diferencia</button>

  <h3>Resultado:</h3>
  <div id="resultado"></div>

  <script>
    function union() {
      var setA = new Set(document.getElementById('setA').value.split(',').map(item => item.trim()));
      var setB = new Set(document.getElementById('setB').value.split(',').map(item => item.trim()));
      var result = new Set([...setA, ...setB]);
      displayResult(result);
    }

    function interseccion() {
      var setA = new Set(document.getElementById('setA').value.split(',').map(item => item.trim()));
      var setB = new Set(document.getElementById('setB').value.split(',').map(item => item.trim()));
      var result = new Set([...setA].filter(x => setB.has(x)));
      displayResult(result);
    }

    function diferencia() {
      var setA = new Set(document.getElementById('setA').value.split(',').map(item => item.trim()));
      var setB = new Set(document.getElementById('setB').value.split(',').map(item => item.trim()));
      var result = new Set([...setA].filter(x => !setB.has(x)));
      displayResult(result);
    }

    function displayResult(result) {
      document.getElementById('resultado').textContent = Array.from(result).join(', ');
    }
  </script>

</body>
</html>
