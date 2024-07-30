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
  src: url("./assets/fonts/Quicksand-VariableFont_wght.ttf");
}

* {
  margin: 0;
}

body {
  background: rgb(0, 0, 0);
  color: white;
}

.app {
  font-size: 11px;
}

.app--foreground {
  position: absolute;
  min-height: 100vh;
  width: 100vw;
}

.nav {
  font-family: "titles";
  min-height: 72px;
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
  max-width: 1000px;
  color: white;
  backdrop-filter: blur(20px);
  border-radius: 5px;
  max-height: calc(100vh - 220px);
  overflow: auto;
  animation-name: fadeIn;
  animation-duration: 1000ms;
  transition: 500ms;
}

.page--cont--A {
  padding: 10px;
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
  font-size: clamp(25px, 4vw, 30px);
  font-family: "titles";
  text-align: center;
  font-weight: 550;
}

.page--subtitle {
  font-size: clamp(15px, 3vw, 20px);
  font-family: "titles";
}

.page--subtitle--span {
  font-size: 11px;
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
</style>
