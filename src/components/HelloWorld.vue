<template>
  <div class="container">
    <div class="game-border">
      <Game/>
    </div>
  </div>
</template>

<script>
import Game from './Game.vue'

export default {
  name: "HelloWorld",
  components: {
    Game
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  background-color: rgb(0, 46, 105);
  width: 100%;
  height: 60vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.game-border{
  width: 600px;
  height: 600px;
  background-color: rgb(201, 114, 114);
}
</style>
