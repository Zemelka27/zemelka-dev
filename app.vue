<template>
  <div class="app">
    <Balls :page="page" />
    <div class="app--foreground">
      <Nav :page="page" @updatePage="updatePage" />
      <div class="page--wrapper">
        <Bio v-if="page === 1" />
        <Portfolio v-if="page === 2" />
        <Contact v-if="page === 3" />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      page: 0,
    };
  },
  methods: {
    updatePage(value) {
      this.page = value;
    },
  },
};
</script>
<style>
@font-face {
  font-family: "titles";
  src: url("./assets/fonts/Cinzel-Variable.ttf");
}
@font-face {
  font-family: "main";
  src: url("./assets/fonts/Sen-Regular.ttf");
}

* {
  margin: 0;
}

body {
  background: rgb(0, 0, 0);
  color: white;
}

.app {
  font-size: clamp(14px, 2vw, 18px);
}

.app--foreground {
  position: absolute;
  min-height: 100vh;
  width: 100vw;
}

.nav {
  font-family: "titles";
  min-height: 130px;
  animation-name: fadeIn;
  animation-duration: 10000ms;
  transition: 500ms;
}

.page--wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  min-height: calc(100vh - 190px);
  font-family: "main";
}

.page {
  max-width: 1500px;
  /* min-width: 500px; */

  /* border: 1px solid black; */
  color: white;
  backdrop-filter: blur(20px);
  border-radius: 20px;
  overflow: hidden;
  animation-name: fadeIn;
  animation-duration: 1000ms;
  transition: 500ms;
}

.page--cont--A {
  padding: 20px;
  background: rgba(0, 0, 0, 0.6);
}

.page--cont--B {
  background: rgba(0, 0, 0, 0.1);
  padding: 20px;
}

.page--cont--C {
  padding: 10px;
  background: rgba(0, 0, 0, 0.3);
}

.page--title {
  font-size: clamp(30px, 6vw, 70px);
  font-family: "titles";
  text-align: center;
}

.page--subtitle {
  font-size: clamp(23px, 5vw, 50px);
  font-family: "titles";
}

@keyframes fadeIn {
  0% {
    opacity: 0%;
  }

  100% {
    opacity: 100%;
  }
}


@media (max-width: 600px) {
.nav{
  min-height: 115px
}
}
</style>
