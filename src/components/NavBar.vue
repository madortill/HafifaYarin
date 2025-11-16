
<template>
  <div class="menu-container">
    <div 
      v-for="(item, index) in menuItems" 
      :key="index"
      class="menu-item"
      :class="{ 'active': isInRange(item.range) }"
      @click="emitIfAllowed(item.range)"
    >
      {{ item.text }}
    </div>
  </div>
</template>
  
<script>
export default {
  name: "NavBar",
  props: {
    selected: {  
      type: Number,
      required: true
    }
  },
  data() {
    return {
      menuItems: [
        { text: "הגדרה", range: [2,2] },
        { text: "סוגי אסטרואידים", range: [3,3] },
        { text: "איך לפוצץ?", range: [4, 6] },
        { text: "תרגול", range: [7,7] }
      ]
    };
  },
  methods: {
    isInRange(range) {
      return this.selected >= range[0] && this.selected <= range[1];
    },

    emitIfAllowed(range) {
      const [startPage] = range;
      this.$emit("select", startPage); 
    }
  }
};
</script>

  <style scoped>
  .menu-container {
    position:fixed;
    display: flex;
    justify-content: space-between;
    align-items: center;
    width:100%;
    top:0ch;
    background-color: #faf9f1;
    overflow: hidden;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    z-index: 9999;
  }
  
  .menu-item {
    flex: 1;
    text-align: center;
    padding: 4vw 0;
    font-family: "Karantina-Light";
    font-size: 2rem;
    cursor: pointer;
    color: #000;
    border-left: 0.5ch solid red;
  }
  
 
  .menu-item:first-child {
    border-left: none;
  }
  
  
  .active {
   font-family: 'karantina-bold';
  }
  </style>
  