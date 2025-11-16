<template>
    <div id="HowToBombPage" class="how-to-bomb-page">
        <div class="how-to-bomb-text">תחנת השיגור היא האחראית לחישוב קואורדינטות שבהן האסטרואיד נמצא בכל רגע נתון. תפקידכם הוא לכוון את משגר הפצצות לכיוון האסטרואיד לפי הקורדינאטות שקיבלתם מתחנת השיגור.
        </div>
    </div>
  </template>


<script>

  export default {
    name: "how-to-bomb-page",
    data() {
      return {};
    }, 
    
  };
  
  </script>
  
  <style scoped>
  
  .how-to-bomb-page {
    background-image: url("../assets/media/background.svg");
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    width: 402px;
    height: 91vh;
    margin: 0;
    padding: 0;
    overflow: hidden;
  }
   
  .how-to-bomb-text {
    display: flex;
    margin-top: 11rem;
    margin-left: 5rem;
    background-color: #fffff6;
    border-radius: 8%;
    height:  18rem;
    width: 15rem;
    color:black;
    font-family: 'karantina-light';
    font-size: 2rem;
    direction: rtl;
    line-height: 2.2rem;
    padding: 1rem;

  }
  </style>
  