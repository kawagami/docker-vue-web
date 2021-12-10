<template>
  <div class="game">
    這是game
    <div class="test-block"></div>
    <button v-on:click="testBlock">按鈕</button>
    <div>
      <button v-if="flag">會不會顯示sgrg465123</button>
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
    testBlock: function () {
      const test = document.querySelector(".test-block");
      test.style.backgroundColor = "black";
      // console.log(123);
      // return true;
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

.test-block {
  width: 100px;
  height: 100px;
  background-color: #fff;
}
</style>
