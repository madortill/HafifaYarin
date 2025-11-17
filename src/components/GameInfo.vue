<template>
    <div id="GameInfo" class="game-info-page">
        <p class="header"> הוראות למשחק</p>
        <div class="interactions"> במשחק זה תצטרכו לאסוף את כל הפריטים על מנת להיות אסטרונאוטים מוכשרים, כשתגיעו לכל פריט תופיע לכם שאלה ןתצטרכו לענות עליה נכון בסיום המשחק תגיעו לעמוד הסיום ותוכלו לראות מה הציון שלכם!!
        </div>
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
    display: flex;
    flex-wrap: wrap;
    align-content: space-around;
    align-items: center;
    justify-content: space-around;
    flex-direction: column;
  }
  
  .header {
   display: flex;
   align-content: center;
   margin-top: 2rem;
    font-size: 7ch;
    color: black; 
    z-index: 10; 
    font-family: "Karantina-Bold";
  }

  .interactions {
    display: flex;
    flex-wrap: wrap;
    background-color:#FFFFF6;
    font-family: 'Karantina-light';
    color: black;
    font-size: 2rem;
    border-radius: 2ch;
    width:15rem;
    height: 20rem;
    direction: rtl;

  }

  .start-button {
    position: absolute;
    bottom: 15vh;
    right: 25vw;
    width: 50vw;

    
    
  }
  </style>