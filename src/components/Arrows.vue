 <template>
    <div>
      <button @click="back" class="back-arrow">  > חזור </button>
      <button @click="forward" class="forward-arrow"> הבא > </button>
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
    .back-arrow {
        background:none;
        position: fixed;
        font-family:'karantrina-regular' ;
        font-size: 5ch;
        top:75vh;
        left:1vw;
        display: flex;
        gap: 20px;
        z-index: 9999;
        color: white;
        border: none;
    }

    .forward-arrow {
        background:none;
        position: fixed;
        font-family:'karantrina-regular' ;
        font-size: 5ch;
        top:75vh;
        left: 70vw;
        display: flex;
        gap: 20px;
        z-index: 9999;
        color: white;
        border: none;
    }

</style>

