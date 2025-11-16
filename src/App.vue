<template>
    <div class="app">
      <open-page v-if="page === 0" @start="page = 1"/>
      <info-page v-if="page === 1" @nextPage="page = 2"/>
      <definition-Page v-if="page === 2"></definition-Page>
      <arrows  v-if="page >=2 && page < 7" @forward="page < 8 && (page += 1)" @back="page > 1 && (page -= 1)"/>
      <nav-bar v-if="page >= 2 && page < 7" :selected="page" @select="handleSelect"> </nav-bar>
      <kinds v-if="page === 3"></kinds>
      <how-to-bomb-page v-if="page === 4"></how-to-bomb-page>
      <how-to-bomb-page-two v-if="page === 5"></how-to-bomb-page-two>
      <how-to-bomb-page-three v-if="page === 6"></how-to-bomb-page-three>
      <game-info v-if="page === 7" @startGame="page = 8"></game-info>
      <game-page v-if="page === 8"></game-page>
    </div>
</template>

<script>
import OpenPage from './components/OpenPage.vue';
// import About from './components/About.vue';
import InfoPage from './components/InfoPage.vue';
import DefinitionPage from './components/DefinitionPage.vue';
import Arrows from './components/Arrows.vue';
import NavBar from './components/NavBar.vue';
import Kinds from './components/Kinds.vue';
import HowToBombPage from './components/HowToBombPage.vue';
import HowToBombPageTwo from './components/HowToBombPageTwo.vue';
import HowToBombPageThree from './components/HowToBombPageThree.vue';
import GameInfo from './components/GameInfo.vue';
import GamePage from './components/GamePage.vue';



export default {
  name: "app",
  components: {
       OpenPage , 
      //  About,
      InfoPage,
    DefinitionPage,
      Arrows,
      NavBar,
      Kinds,
    HowToBombPage,
    HowToBombPageTwo,
    HowToBombPageThree,
    GameInfo,
    GamePage,
      },
  data() {
        return {
          page: 0,
        }
    },
   methods: {
    handleSelect(targetPage) {
      if (this.page >= 2) {
        this.page = targetPage;
      }
   }
  }
  };
</script>

<style scoped>
  @font-face {
    font-family: "Karantina-Regular";
    src: url('../src/assets/fonts/Karantina-Regular.ttf');
}

  @font-face {
    font-family: "Karantina-Light";
    src: url('../src/assets/fonts/Karantina-Light.ttf');
}

@font-face {
    font-family: "Karantina-Bold";
    src: url('../src/assets/fonts/Karantina-Bold.ttf');
}

html {
	font-size: calc(10px + 0.5vw);
}


</style> 
