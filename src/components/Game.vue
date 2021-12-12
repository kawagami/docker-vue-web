<template>
  <!-- <button v-on:click="testBlock">按鈕</button> -->
  <div class="game">
    <div class="game-middle" v-for="x in gameArray" :key="x">
      <div class="game-inner" v-for="y in x" :key="y">
        <div class="game-unit" v-if="y" style="background-color: #fff">
          {{ y }}
        </div>
        <div class="game-unit" v-else style="background-color: #000">
          {{ y }}
        </div>
      </div>
    </div>
  </div>
  <div>
    {{ KeyboardNow }}
  </div>
</template>

<script>
export default {
  name: "Game",
  data() {
    return {
      KeyboardNow: "這裡會顯示按了什麼按鈕",
      gameArray: [],
    };
  },
  methods: {
    formatGameArray: function () {
      for (let i = 0; i < 10; i++) {
        this.gameArray[i] = [];
        for (let j = 0; j < 10; j++) {
          // this.gameArray[i][j] = `${i} ${j}`;
          // this.gameArray[i][j] = `${Math.round(Math.random())}`;
          this.gameArray[i][j] = Math.round(Math.random());
        }
      }
    },
    outputView: function () {
      let map = this.gameArray;
      map.forEach(function (x) {
        x.forEach(function (y) {
          console.log(y);
          // return ture;
        });
      });
    },
    keyboardWatch: function () {
      document.onkeydown = (e) => {
        // console.log(window.event);
        let el =
          e || event || window.event || arguments.callee.caller.arguments[0];
        this.KeyboardNow = el.code;
        // if (el && el.keyCode == 37) {
        //   console.log("左");
        // } else if (el && el.keyCode == 38) {
        //   console.log("上");
        // } else if (el && el.keyCode == 39) {
        //   console.log("右");
        // } else if (el && el.keyCode == 40) {
        //   console.log("下");
        // }
        if (el && el.code === "ArrowLeft") {
          console.log("左");
        } else if (el && el.code === "ArrowUp") {
          console.log("上");
        } else if (el && el.code === "ArrowRight") {
          console.log("右");
        } else if (el && el.code === "ArrowDown") {
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
    },
  },
  // created() {
  //   console.log("這裡是created");
  // },
  mounted() {
    // 生成遊戲空 array
    this.formatGameArray();

    // 生成遊戲畫面
    // this.outputView();

    // 監控鍵盤事件
    this.keyboardWatch();
    // console.log(this.gameArray);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.game {
  width: 100%;
  height: 100%;
  background-color: rgb(180, 48, 48);
  display: flex;
  /* flex-direction: column; */
  /* justify-content: space-evenly; */
  /* align-items: stretch; */
}

.game-middle {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  /* align-items: stretch; */
  justify-content: space-evenly;
}

.game-inner {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.game-unit {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* .test-block {
  width: 100px;
  height: 100px;
  background-color: #fff;
} */
</style>
