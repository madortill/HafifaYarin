<template>
  <div id="OpenPage" class="open-page">
   <p class="header">לומדת פיצוץ אסטרואידים</p>
   <button @click="start" class="start-button">
    התחל
   </button>
  </div>
</template>

<script>
export default {
  name: "open-page",
  data() {
    return {
      
    };
  },
  methods: {
    start() {
      this.$emit("start");
    },
  }
};


</script>

<style scoped>
.open-page {
  background-image: url("../assets/media/background.svg");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  width: 100%;
  height: 91vh;
  margin: 0;
  padding: 0;
  overflow: hidden;
}

.header {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin-top: 8rem;
  margin-left: 6rem; 
  font-size: 7ch;
  color: white; 
  font-family: "Karantina-Bold";

}

.start-button {
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin-left: 6rem;
  margin-top: 24rem;
  background-color: #ffc814;
  font-family: 'Karantina-Bold';
  color: white;
  font-size: 10ch;
  border-radius: 2ch;
  width: 12rem;
  height: 5.5rem;
  
}

</style>
