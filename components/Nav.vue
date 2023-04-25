<template>
  <div class="nav" ref="navRef">
    <div class="nav--cont" ref="navContRef">
      <div class="nav--grid" ref="navGridRef">
        <div class="nav--grid--A" ref="navGridRefA">
          <span @click="setPageAndNavState(0, 0)"
            >Jan Zemelka JS Developer</span
          >
        </div>
        <div class="nav--grid--B" ref="navGridRefB">
          <span ref="navBio" v-on:click="setPageAndNavState(1, 1)"
            >Biography</span
          >
          <span ref="navPort" v-on:click="setPageAndNavState(1, 2)"
            >Portfolio</span
          >
          <span ref="navCont" v-on:click="setPageAndNavState(1, 3)"
            >Contact</span
          >
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      navState: 0,
    };
  },
  props: ["page"],
  mounted() {
    this.setPageAndNavState(0, 0);
  },
  methods: {
    setPageAndNavState(number1, number2) {
      this.navState = number1;
      if (this.navState === 0) {
        this.$refs.navRef.style = "background: rgba(0,0,0,0);";
        this.$refs.navContRef.style =
          "transform: translateX(-50%) translateY(-50%); top: 50%";
        this.$refs.navGridRefA.style =
          "font-size: clamp(25px, 4vw, 50px); cursor: default;";
        this.$refs.navGridRefB.style = "font-size: clamp(14px, 3vw, 20px);";
        this.$emit("updatePage", number2);
      } else if (this.navState === 1) {
        this.$refs.navRef.style = "background: rgba(0,0,0,0.8);";
        this.$refs.navContRef.style =
          "transform: translateX(-50%) translateY(0%); top: 0%";
        this.$refs.navGridRefA.style =
          "font-size: clamp(18px, 5vw, 20px); cursor: pointer;";
        this.$refs.navGridRefB.style = "font-size: 13px;";
        this.$emit("updatePage", number2);
      }

        // if (this.page === 0) {
        //   this.$refs.navBio.style.fontWeight = "normal";
        //   this.$refs.navPort.style.fontWeight = "normal";
        //   this.$refs.navCont.style.fontWeight = "normal";
        // } else if (this.page === 1) {
        //   this.$refs.navBio.style.fontWeight = "bold;";
        //   this.$refs.navPort.style.fontWeight = "normal";
        //   this.$refs.navCont.style.fontWeight = "normal";
        //   console.log(this.$refs.navBio);
        // } else if (this.page === 2) {
        //   this.$refs.navBio.style.fontWeight = "normal";
        //   this.$refs.navPort.style.fontWeight = "bold";
        //   this.$refs.navCont.style.fontWeight = "normal";
        // } else if (this.page === 3) {
        //   this.$refs.navBio.style.fontWeight = "normal";
        //   this.$refs.navPort.style.fontWeight = "normal";
        //   this.$refs.navCont.style.fontWeight = "bold";
        // }
    },
  },
};
</script>
<style>
.nav--cont {
  width: 100%;
  position: absolute;
  transform: translateX(-50%) translateY(-50%);
  left: 50%;
  transition: 500ms;
}

.nav--grid {
  display: grid;
  grid-template-areas:
    "A"
    "B";
  text-align: center;
  /* transition: 500ms; */
}

.nav--grid--A {
  grid-area: A;
  font-weight: bold;
  padding-top: 10px;
  padding-bottom: 5px;
}

.nav--grid--A > span {
  /* padding: 20px; */
  transition: 500ms;
  text-transform: uppercase;
}

.nav--grid--B {
  grid-area: B;
}

.nav--grid--B > span {
  padding-left: 10px;
  padding-right: 10px;
  cursor: pointer;
  transition: 500ms;
}

.nav--grid--B > span:hover {
  font-weight: bold;
}
</style>
