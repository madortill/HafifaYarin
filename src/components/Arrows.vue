 <template>
    <div class="arrows">
      <button @click="back" class="back-arrow"> חזור </button>
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
    position: fixed;
  top: 42rem;       
  left: 0.5rem;
  width: 90%;

  display: flex;
  justify-content: space-between;
  align-items: center;

  z-index: 9999;
   
   }
  .back-arrow {
    background: none;
  font-family: 'karantrina-regular';
  font-size: 5ch;
  color: white;
  border: none;
 
    }

  .forward-arrow {
    background: none;
  font-family: 'karantrina-regular';
  font-size: 5ch;
  color: white;
  border: none;
 
    }

</style>

