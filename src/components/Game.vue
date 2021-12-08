<template>
  <div class="game">
    這是game
    <button v-on:click="sumSomething">按鈕</button>
    <div>
      <button v-if="flag">會不會顯示</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Game",
  data() {
    return {
      flag: true,
    };
  },
  methods: {
    sumSomething: function () {
      return (this.flag = !this.flag);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.game {
  width: 100%;
  height: 100%;
  background-color: rgb(180, 48, 48);
}
</style>
