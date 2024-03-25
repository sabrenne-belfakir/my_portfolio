 <script>
    import { onMount } from 'svelte';
  
    onMount(() => {
      const pokedex = document.getElementById('pokedex');
  
      if (pokedex) {
        pokedex.addEventListener('click', function() {
          this.classList.toggle('closed');
        });
      }
    });
  </script>
  
  <style>
      .pokedex {
    left: 100px;
    position: relative;
  }
  .pokedex > .pokedex-separator,
  .pokedex > .pokedex-bottom-part {
    background: #f00;
    border: 2px solid #000;
  }
  .pokedex-flap {
    width: 100%;
    height: 100%;
    position: absolute;
    transform-style: preserve-3d;
    transition: transform 1s;
    transform: rotateX(360deg);
    transform-origin: 0% 100%;
  }
  .pokedex-flap figure {
    margin: 0;
    display: block;
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
    -webkit-backface-visibility: hidden;
  }
  .pokedex-flap > .pokedex-flap-front {
    transform: rotateX(180deg);
  }
  .pokedex-flap-front,
  .pokedex-flap-back {
    background: #f00;
    border: 2px solid #000;
  }
  .pokedex-flap-back {
    border-top-right-radius: 25px;
    border-top-left-radius: 10px;
  }
  .pokedex-flap-front {
    border-bottom-right-radius: 25px;
    border-bottom-left-radius: 25px;
  }
  .pokedex-flap-back:before {
    content: ' ';
    position: absolute;
    background: #f00;
    border: 2px solid #000;
    border-right-width: 0;
    width: 50px;
    height: 100px;
    margin-left: -52px;
    margin-top: 23px;
    border-top-left-radius: 50px;
    border-bottom-left-radius: 50px;
  }
  .pokedex.closed .pokedex-flap {
    transform: rotateX(180deg) translate(0px, -14px);
  }
  .pokedex > .pokedex-top-part {
    position: relative;
    perspective: 800px;
    width: 230px;
    height: 150px;
    margin-left: 70px;
    position: relative;
    z-index: 11;
  }
  .pokedex > .pokedex-separator {
    width: 230px;
    margin-left: 70px;
    height: 10px;
    border-bottom-width: 0;
    position: relative;
    z-index: 10;
  }
  .pokedex > .pokedex-bottom-part {
    width: 300px;
    height: 150px;
    border-top-left-radius: 75px;
    border-bottom-left-radius: 75px;
    border-bottom-right-radius: 25px;
    position: relative;
    z-index: 10;
    display: flex;
    flex-direction: row;
  }
  .pokedex-joystick {
    content: ' ';
    background: #333;
    width: 100px;
    height: 100px;
    position: absolute;
    margin-left: 300px;
    z-index: 1;
    margin-top: -130px;
    border: 2px solid #000;
    border-top-right-radius: 50px;
    border-bottom-right-radius: 50px;
    left: 0px;
    transition: left 1s ease;
  }
  .pokedex-joystick-tracker {
    background: #d3d3d3;
    border: 2px solid #000;
    margin: 3px;
    width: 90px;
    height: 90px;
    border-radius: 50%;
  }
  .pokedex-joystick-tracker:before,
  .pokedex-joystick-tracker:after {
    content: ' ';
    position: absolute;
  }
  .pokedex-joystick-tracker:before {
    border: 2px solid #333;
    width: 70px;
    height: 70px;
    border-radius: 50%;
    margin-top: 8px;
    margin-left: 8px;
  }
  .pokedex-joystick-tracker:after {
    height: 10px;
    width: 10px;
    background: #333;
    margin-left: 20px;
    margin-top: -2px;
    border-radius: 50%;
  }
  .pokedex-joystick-button {
    background: #90ee90;
    width: 50px;
    height: 50px;
    border: 2px solid #333;
    border-radius: 50%;
    margin-top: 18px;
    margin-left: 18px;
  }
  .pokedex-top-screen,
  .pokedex-bottom-screen {
    border: 4px solid #000;
    border-radius: 8px;
    background: #add8e6;
    color: #00008b;
    padding: 8px;
    height: 100px;
    margin: 12px;
    margin-left: 34px;
  }
  .pokedex-top-screen {
    margin-left: 24px;
  }
  .pokedex-bottom-screen {
    flex: 1;
  }
  .pokedex-pad-background {
    width: 66px;
    background: #333;
    border-top-left-radius: 75px;
    border-bottom-left-radius: 75px;
    border-right: 4px solid #000;
  }
  .pokedex-pad-background:before {
    content: ' ';
    position: absolute;
    width: 12px;
    height: 6px;
    background: #006400;
    margin-top: 70px;
    border: 2px solid #000;
    border-left-width: 0;
  }
  .pokedex-pad {
    position: absolute;
    background: #d3d3d3;
    height: 85px;
    width: 85px;
    margin-top: 30px;
    margin-left: 17px;
    border-top-left-radius: 41px;
    border-bottom-left-radius: 41px;
    border: 2px solid #000;
    border-right-width: 0;
  }
  .pokedex-pad:before,
  .pokedex-pad:after {
    content: ' ';
    position: absolute;
    background: #333;
    width: 50px;
    height: 15px;
    margin-top: 35px;
    margin-left: 20px;
  }
  .pokedex-pad:after {
    transform: rotate(0deg);
  }
  .pokedex-pad-circle {
    width: 65px;
    height: 65px;
    border-radius: 50%;
    position: absolute;
    border: 2px solid #a9a9a9;
    margin-top: 40px;
    margin-left: 30px;
  }
  .pokedex.closed .pokedex-joystick {
    left: -100px;
  }
  #btn {
    position: fixed;
    top: 0;
    right: 0;
  }
  
  </style>     
    <div class="pokedex closed" id="pokedex">
        <div class="pokedex-top-part">
          <div class="pokedex-flap">
            <figure class="pokedex-flap-front"></figure>
            <figure class="pokedex-flap-back">
              <div class="pokedex-top-screen">Loading...</div>
            </figure>
          </div>
        </div>
        <div class="pokedex-separator"></div>
        <div class="pokedex-bottom-part">
          <div class="pokedex-pad-background">
            <div class="pokedex-pad"></div>
            <div class="pokedex-pad-circle"></div>
          </div>
          <div class="pokedex-bottom-screen"></div>
        </div>
        <div class="pokedex-joystick">
          <div class="pokedex-joystick-tracker">
            <div class="pokedex-joystick-button"></div>
          </div>
        </div>
      </div>
  
  