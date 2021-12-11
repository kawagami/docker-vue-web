<template>
  <div class="game">
    <div class="test-block"></div>
    <button v-on:click="testBlock">按鈕</button>
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
    keyDown: function () {
      document.onkeydown = (e) => {
        let el =
          e || event || window.event || arguments.callee.caller.arguments[0];
        if (el && el.keyCode == 37) {
          console.log("左");
        } else if (el && el.keyCode == 38) {
          console.log("上");
        } else if (el && el.keyCode == 39) {
          console.log("右");
        } else if (el && el.keyCode == 40) {
          console.log("下");
        }
      };
    },
    testBlock: function () {
      const test = document.querySelector(".game");
      const one = Math.floor(Math.random() * 255);
      const two = Math.floor(Math.random() * 255);
      const three = Math.floor(Math.random() * 255);
      test.style.backgroundColor = `rgb(${one}, ${two}, ${three})`;
      // this.addEventListener("keypress", (event) => {
      //   if (event.keyCode == 40) {
      //     alert("hi.");
      //   }
      // });
      // const aaa =  document.querySelector('.game')
      // aaa.style.display = 'none';
      // console.log(123);
      // return true;
    },
  },
  // created() {
  //   console.log("這裡是created");
  // },
  mounted() {
    this.keyDown();
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

/* .test-block {
  width: 100px;
  height: 100px;
  background-color: #fff;
} */
</style>
