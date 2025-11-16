<template>
    <div id="HowToBombPageTwo" class="how-to-bomb-page-two">
      <img src="src/assets/media/Artboard36.svg" alt="astroid" class="astroid"/>
      <div class="text"> 11h 46m 13s -24° 25' 40"</div>
        <img src="src/assets/media/Halalit.png" alt="halalit" class="halalit"/>  
       
    </div>
  </template>


<script>

  export default {
    name: "how-to-bomb-page-two",
    data() {
      return {};
    }, 
    
  };
  
  </script>
  
  <style scoped>
  .how-to-bomb-page-two  {
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
   
  .astroid {
    display: flex;
    margin-top: 6rem;
    margin-left: 50%;
    transform: rotate(-10deg);
    width: 12rem;

  }

  .text {
    display: flex;
    background-color: #fffff6;
    border-radius: 20%;
    height: 2.5rem;
    width: 8rem;
    margin-top: 13rem;
    margin-left: 30%;
    font-size: 1rem;
    padding-left: 2%;
    color:black;
  }
  
  .halalit {
    display: flex;
    margin-top: 1rem;
    margin-left: 50%;
    transform: translateX(-50%);
    width: 15rem;
    z-index: 10;
  }
  
  </style>
  