<template>
    <div id="GameInfo" class="game-info-page">
        <p class="header"> הוראות למשחק</p>
        <div class="interactions"></div>
        <button @click= "startGame">
            <img src="../assets/media/התחל.png" class="start-button"/>
        </button>
    </div>
  </template>
  
  <script>
  export default {
    name: "gane-info",
    data() {
      return {
        
      };
    },
    methods: {
      startGame() {
        this.$emit("startGame");
      },
    }
  };
  
  
  </script>
  
  <style scoped>
  .game-info-page {
    background-image: url("../assets/media/game.png");
    background-color: #fffff6 ;
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    width: 402px; 
    height: 85vh;
    margin: 0;
    padding: 0;
    overflow: hidden;
  }
  
  .header {
   display: flex;
    margin-top: 3rem; 
    margin-left: 5rem; 
    font-size: 7ch;
    color: black; 
    z-index: 10; 
    font-family: "Karantina-Bold";
  }

  .interactions {
    display: flex;
    flex-wrap: wrap;
    background-color:#FFFFF6;
    margin-top: 2rem;
    margin-left: 3.9rem;
    font-family: 'Karantina-light';
    color: black;
    font-size: 2rem;
    border-radius: 2ch;
    width:17rem;
    height: 25rem;
    direction: rtl;

  }

  .start-button {
    position: absolute;
    bottom: 15vh;
    right: 25vw;
  
    width: 50vw;
    
    
  }
  </style>