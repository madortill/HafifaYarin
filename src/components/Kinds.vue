
<template>
    <div class="kinds-page">
      <div v-for="(item, index) in cards" :key="index" class="card">
        <div class="text">
          <p>{{ item.text }}</p>
        </div>
        <div class="image">
          <img :src="item.image" alt="תמונה" />
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "Kinds",
    data() {
      return {
        cards: [
          { text: "אסטרואיד בייבי - אסטרואיד ממש קטן והורס רק שכונות מקומיות." , image : '../src/assets/media/אסטרואיד-ילד.png'},
          { text: "אסטרואיד נער מתבגר - אסטרואיד שהוא די חרא כי הוא בכוונה מנסה להפציץ מקומות שהוא לא אוהב.", image : '../src/assets/media/אסטרואיד-מתבגר.png' },
          { text: ". אסטרואיד בוגר - אסטרואיד ממש גדול שיכול להשמיד את כל כדור הארץ." , image : '../src/assets/media/אסטרואיד-זקן.png' }
        ]
      };
    }
  };
  </script>
  
  <style scoped>
  .kinds-page {
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
  
  
  .card {
  display: flex;
  justify-content: space-between;
  width: 25rem;
  height: 8rem;
  border-radius: 10%;
  overflow: hidden;
  background-color: white;
  margin: 1rem auto; 

}

.card:first-child {
  margin-top: 8rem;
}
  
  
  .text {
    background-color: #fefef3;
    flex: 1;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: "Karantina-light";
    font-size: 1.8rem;
    text-align: center;
    padding: 1rem;
  }
  
 
  .image {
    background-color: #d3d3d3;
    flex: 1;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  
  .image img {
    width: 80%;
    height: auto;
    object-fit: contain;
  }
  </style>