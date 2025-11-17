<template>
    <div id="Finish" class="finish-page">
        <p class="header"> סיימת!!</p>
        <div class="info"> סיימת את לומדת באסטרואידים בהצלחה! כעת אתם אסטרונאוטים מוסמכים ויכולים להציל את העולם - במידת הצורך
        </div>
        <button @click="backLomda" class="back-button"> חזור ללומדה
        </button>
    </div>
  </template>
  
  <script>
  export default {
    name: "finish",
    data() {
      return {
        
      };
    },
    methods: {
      backLomda() {
        this.$emit("backLomda");
      },
    }
  };
  
  
  </script>
  
  <style scoped>
  .finish-page {
    background-image: url("../assets/media/game.png");
    background-color: #fffff6 ;
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    width: 100%; 
    height: 90vh;
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

  .info {
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
    text-align: center;

  }

  .back-button {
   display: flex;
   background-color:rgb(233, 198, 134);
   color: white;
    height: 3rem;
    border: none;
    font-size: 2rem;

    
    
  }
  </style>