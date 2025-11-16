<template>
    <div id="HowToBombPageTwo" class="how-to-bomb-page-three">
        <img src="src/assets/media/Artboard36.svg" alt="astroid" class="astroid" :class="{ moved: isFired }"/>
        <img :src="laserImage" alt="laser" class="laser" :class="{fired: isFired}"/>
        <div class="text"> {{text}}</div>
    </div>
  </template>


<script>

export default {
  name: "how-to-bomb-page-three",
  data() {
    return {
      isFired: false,
      text: "12h 46m 13s -24° 25' 990\"",
      laserImage: "src/assets/media/Artboard40.svg",
      astroidImage: "src/assets/media/Artboard36.svg"
    };
  },
  mounted() {
    setTimeout(() => {
      this.isFired = true;
      this.laserImage = "src/assets/media/Artboard40.svg";
      this.astroidImage = "src/assets/media/explode.png"; 

      this.text = "11h 46m 13s -24° 25' 40";
    }, 1000);
  }
};
  
  </script>
  
  <style scoped>
  .how-to-bomb-page-three  {
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
    margin-left: 55%;
    transform: rotate(-10deg);
    width: 12rem;
    z-index: 9999;
    transition: all 1s ease-in-out;
  }

  .astroid.moved {
  transform: translate(15px, 10px) rotate(2deg);
}

  .text {
    background-color: #fffff6;
    height: 2.5rem;
    width: 8rem;
    margin-left: 50%;
    font-size: 1rem;
    padding-left: 2%;
    z-index: 9999;
    color:black;
    display: flex;
    align-items: center;
    transition: all 1s ease-in-out;
  }
   
  .laser {
    display: flex;
    margin-top: 7rem;
    margin-left: 14%;
    transform: rotate(18deg);
    width: 5rem;
    z-index: 9999;
    transition: all 0.7s ease-in-out;
  }
  .laser.fired {
    margin-top: 7rem;
    margin-left: 14%;
    width: 5rem;
  transform: translateX(20px) rotate(36deg);
 
}
  
  
  </style>
  