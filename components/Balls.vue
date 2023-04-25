<template>
  <div class="balls--arena" ref="ballsArenaRef">
    <div
      class="ball"
      v-for="ball in ballsData"
      :key="ball.id"
      ref="ballsRefs"
    ></div>
  </div>
</template>
<script>
export default {
  props: ["page"],
  data() {
    return {
      windowWidth: 1000,
      windowHeight: 1000,
      ballsData: [],
      ballsAmount: 60,
      ballDiameterK: 1000/ 2.5,
      ballsSpeedK: 0.4,
    };
  },
  watch: {
    page() {
      this.changeBallsColor();
    },
  },
  created() {
    this.setBallsData();
  },
  mounted() {
    this.setBallsArena();
    this.watchWindowWidth();
    this.setBallsDivs();
    this.ballsAnimation();
    this.changeBallsColor();
  },
  methods: {
    watchWindowWidth() {
      window.addEventListener("resize", () => {
        this.windowWidth = window.innerWidth;
        this.windowHeight = window.innerHeight;
        this.setBallsArena();
      });
    },
    setBallsArena() {
      this.$refs.ballsArenaRef.style.width = this.windowWidth + "px";
      this.$refs.ballsArenaRef.style.height = this.windowHeight + "px";
    },
    setBallsData() {
      for (let index = 0; index < this.ballsAmount; index++) {
        let ball = new Object();

        ball.diameter = parseInt(Math.random() * this.ballDiameterK);
        ball.radius = ball.diameter / 2;
        ball.x = parseInt(Math.random() * this.windowWidth);
        if (ball.x + ball.diameter > this.windowWidth) {
          ball.x = ball.x - (ball.x + ball.diameter - this.windowWidth);
        }
        ball.y = parseInt(Math.random() * this.windowHeight);
        if (ball.y + ball.diameter > this.windowHeight) {
          ball.y = ball.y - (ball.y + ball.diameter - this.windowHeight);
        }
        ball.xDirection = Math.random() <= 0.5;
        ball.yDirection = Math.random() <= 0.5;
        ball.randomSpeedX = Math.random() * this.ballsSpeedK;
        ball.randomSpeedY = Math.random() * this.ballsSpeedK;

        // ----------------Push-Data-----------------------------------------------
        this.ballsData.push(ball);
      }
    },
    setBallsDivs() {
      for (let index = 0; index < this.ballsAmount; index++) {
        let ballDiv = this.$refs.ballsRefs[index];
        let ballData = this.ballsData[index];

        ballDiv.style.width = ballData.diameter + "px";
        ballDiv.style.height = ballData.diameter + "px";
        ballDiv.style.left = ballData.x + "px";
        ballDiv.style.top = ballData.y + "px";
      }
    },
    setBallsMovement() {
      for (let index = 0; index < this.ballsAmount; index++) {
        let ballDiv = this.$refs.ballsRefs[index];
        let ballData = this.ballsData[index];

        // ----------------------X-Axis-------------------------------------------
        if (ballData.x <= 0) {
          ballData.xDirection = true;
        } else if (ballData.x >= this.windowWidth - ballData.diameter) {
          ballData.xDirection = false;
        }
        if (ballData.xDirection == true) {
          ballData.x += ballData.randomSpeedX;
          ballDiv.style.left = ballData.x + "px";
        } else if (ballData.xDirection == false) {
          ballData.x -= ballData.randomSpeedX;
          ballDiv.style.left = ballData.x + "px";
        }
        // ----------------------Y-Axis-------------------------------------------
        if (ballData.y <= 0) {
          ballData.yDirection = true;
        } else if (ballData.y >= this.windowHeight - ballData.diameter) {
          ballData.yDirection = false;
        }
        if (ballData.yDirection == true) {
          ballData.y += ballData.randomSpeedY;
          ballDiv.style.top = ballData.y + "px";
        } else if (ballData.yDirection == false) {
          ballData.y -= ballData.randomSpeedY;
          ballDiv.style.top = ballData.y + "px";
        }
      }
    },
    ballsAnimation() {
      requestAnimationFrame(this.ballsAnimation);
      this.setBallsMovement();
    },
    changeBallsColor() {
      for (let index = 0; index < this.ballsAmount; index++) {
        let ballDiv = this.$refs.ballsRefs[index];
        if (this.page === 0) {
          ballDiv.style.boxShadow = "0px 0px 40px 15px #F24236";
        } else if (this.page === 1) {
          ballDiv.style.boxShadow = "0px 0px 40px 15px #1982C4";
        } else if (this.page === 2) {
          ballDiv.style.boxShadow = "0px 0px 40px 15px #8AC926";
        } else if (this.page === 3) {
          ballDiv.style.boxShadow = "0px 0px 40px 15px #FFCA3A";
        }
      }
    },
  },
};
</script>
<style>
.balls--arena {
  position: absolute;
  overflow: hidden;
  z-index: 0;
  width: 100vw;
  height: 100vh;
}
.ball {
  position: absolute;
  border-radius: 100%;
  opacity: 0.3;
  transition: box-shadow 2000ms;
  z-index: 1;
  animation-name: fadeInBalls;
  animation-duration: 10000ms;
}

@keyframes fadeInBalls {
  0% {
    opacity: 0%;
  }

  100% {
    opacity: 30%;
  }
}
</style>
