
<template>
    <div class="game-page">
      <matrix @collect-item="addCollect" @change="move"></matrix>
      
      <div class="collects">Your collects: {{ collected }}</div>
    </div>
  </template>
  
  <script>
  import Matrix from "./Matrix.vue";
  
  export default {
    name: "GamePage",
    components: { Matrix },
    data() {
      return {
        collected: 0,
      };
    },
    methods: {
      addCollect() {
        this.collected++;
      },
      move() {
        console.log('in');
        this.$emit("finish")
       
      }
    },
   
  };
  </script>
  
  <style scoped>
  .game-page {
    background-color: #fffff6;
    height: 91vh;
   
  }
  
  .collects {
    display: flex;
    margin-top: 7rem;
    margin-left: 2.5rem;
    width: 9rem;
    font-family: "karantina-light";
    font-size: 3.5rem;
  }
  </style>