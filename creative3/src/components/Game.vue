<template>
  <div class="grid" v-bind:board="board">
    <div class="cell" v-for="cell in board" v-bind:key="cell" @click="cell.move = playerToken">
        <button> {{cell.move}} </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "tickTackToe",
  data() {
    return {
     board: [
       {move: ""},
       {move: ""},
       {move: ""},
       {move: ""},
       {move: ""},
       {move: ""},
       {move: ""},
       {move: ""},
       {move: ""},
     ]
    }
  },
  methods: {
  },
  computed: {
    playerToken()  {
      return "X";
      //this.move = "X"; //when trying to move this computed to method, it breaks!!
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.grid {
  display: flex;
  /* establish flex container */
  flex-wrap: wrap;
  /* enable flex items to wrap */
  justify-content: space-around;
  width: 150px;

}

.cell {
  flex: 0 0 32%;
  /* don't grow, don't shrink, width */
  height: 50px;
  margin-bottom: 5px;
  background-color: #999;
}
</style>
