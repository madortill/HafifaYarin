 <template>
    <div class="arrows">
      <button @click="back" class="back-arrow">   חזור </button>
      <button @click="forward" class="forward-arrow"> הבא  </button>
    </div>
  </template>
  
  <script>
  export default {
    name: "ArrowButtons",
    data() {
        return{};
    },

    methods: {
        forward() {
         this.$emit("forward" ,+1);
      },
      back() {
         this.$emit("back" ,-1);
      },
    }
  };
  </script> 

  <style> 
  .arrows {
    position: absolute;
  bottom: 2rem;       
  left: 0;
  width: 100%;

  display: flex;
  justify-content: space-between;
  align-items: center;

  z-index: 20;
  padding: 0 2rem; 
   
   }
  .back-arrow {
    background: none;
  font-family: 'karantrina-regular';
  font-size: 5ch;
  color: white;
  border: none;
  z-index: 30;
    }

  .forward-arrow {
    background: none;
  font-family: 'karantrina-regular';
  font-size: 5ch;
  color: white;
  border: none;
  z-index: 30;
    }

</style>

