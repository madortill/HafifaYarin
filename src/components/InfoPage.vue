<template>
    <div id="InfoPage" class="info-page" >
      <p class="header">הוראות</p>  
      <div class="interactions">שיעור פיצוץ אסטרואיד ידוע בחשיבותו בגלל הסכנה היומיומית הנשקפת לכדור הארץ בלעדיו. עשרות אלפי אסטרואידים נעים ברגע זה לכיוון הכוכב שלנו, ועליכן לדעת כיצד למנוע מהם להגיע אליו
        בלומדה זו נלמד על אסטרואידים, סוגי אסטרואידים , איך לפוצץ אותם לפי קואורדינטות שנקבל מתחנת החלל וכיוון הלייזר. 

      </div> 
      <button @click="nextPage" class="starting-button"> נתחיל לפוצץ</button>  
    </div>
  </template>
  
  <script>
  export default {
    name: "info-page",
    data() {
      return {};
    },
    methods: {
      nextPage() {
        this.$emit("nextPage");
    },
  
    }
  };
  
  
  </script>
  
  <style scoped>
  .info-page {
    background-image: url("/media/background.svg");
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    width: 402px;
    height: 91vh;
    margin: 0;
    padding: 0;
    overflow: hidden;
  }
  
  .header {
    display: flex;
    margin-left:8rem ;
    font-size: 7ch;
    color: white; 
    margin-bottom: 0.5rem;
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
    width:15.5rem;
    height: 20rem;
    direction: rtl;
    padding: 1rem;

  }

  .starting-button {             
    display: flex;
    background-color: #ffc814;
    font-family: 'Karantina-Bold';
    color: white;
    font-size: 5ch;
    border-radius: 2ch;
    flex-direction: column;
    justify-content: center;
    margin-left: 6.5rem;
    margin-top: 4rem;
    width: 12rem;
    height: 5.5rem;
  }
  
  </style>
  