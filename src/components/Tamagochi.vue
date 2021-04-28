<template>
  <div class="tamagochi-container">
      <div class="marca">BOHIO_GOCHI</div>
      <div class="pantalla">
          <div class="salud">
              <img v-for="(point) in 5" :key="point" width="10" :src="point - 1 < salud ? heart_icons.full : heart_icons.empty">
          </div>
          <div class="animalito">
              {{estados_de_salud[salud]}}
          </div>
      </div>
      <nav class="botones">
          <button></button>
          <button></button>
          <button @click="alimentar"></button>
      </nav>
  </div>
</template>

<script>
  export default {
      mounted(){
          setInterval(()=> {
              if(this.salud){
                  this.salud--;
              }
          }, 10000)
      },
      data(){
          return {
              heart_icons: {
                  full: '/assets/heart-solid.svg',
                  empty: '/assets/heart-regular.svg'
              },
              salud: 5,
              estados_de_salud: {
                  0: "💀",
                  1: "🤢",
                  2: "🥺",
                  3: "🐻",
                  4: "😊",
                  5: "😃"
              }
          }
      },
      methods :{
          alimentar(){
              if(this.salud < 5){
                  this.salud++;
              }
          }
      }
  }
</script>

<style lang="scss">
    .tamagochi-container {
        display: grid;
        grid-template-areas: "marca"
                             "pantalla"
                             "botones";
        grid-template-rows: 60px 160px 30px;
        height: 300px;
        width: 250px;
        background: lightpink;
        border-radius: 150px 150px 120px 120px;
        padding: 15px;
        box-sizing: border-box;

        .marca {
            grid-area: marca;
            font-weight: bold;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .pantalla {
            grid-area: pantalla;
            background: url('/assets/bg.webp');
            background-size: 110%;
            background-position: center; 
            width: 80%;
            margin: 10px auto;
            border: 2px solid black;
            position: relative;

            .salud {
                display: flex;
                gap: 2px;
                padding: 5px;
            }

            .animalito{
                position: absolute;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%) scale(4);
            }
        }
        .botones {
            grid-area: botones;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;

            button {
                height: 25px;
                width: 25px;
                border-radius: 50%;
            }
        }
    }
</style>