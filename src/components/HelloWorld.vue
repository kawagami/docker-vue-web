<template>
  <div class="container">
    <div class="game-border"></div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  background-color: rgb(0, 255, 128);
  width: 100%;
  height: 60vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.game-border{
  width: 60%;
  height: 100%;
  background-color: #faa;
}
</style>
