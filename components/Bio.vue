<template>
  <div class="page">
    <div class="page--cont--A">
      <p class="page--title">Biography</p>
    </div>
    <div class="page--cont--B">
      <div class="bio--text">
        <img class="bio--image" src="../assets/images/me.jpeg" />
        <p class="page--subtitle">Hi there,</p>
        <p>&nbsp;</p>
        <p>
          I am a full-stack developer with professional experience since 2020,
          working for various companies across Germany and Mexico.
        </p>
        <p>&nbsp;</p>
        <p>
          My technical expertise spans modern web development frameworks and
          tools, including React, Next.js, Vue.js, Nuxt.js, and Node.js, PHP,
          Java as well as foundational technologies like Vanilla JavaScript,
          HTML and CSS.
        </p>
        <p>&nbsp;</p>
        <p>
          I hold a Bachelor of Engineering in Audiovisual Media from Hochschule
          der Medien in Stuttgart, complemented by an Erasmus program in
          Audiovisual Communication at Universidad Rey Juan Carlos in Madrid. To
          stay ahead in my field, I have further enriched my skills through
          specialized online courses.
        </p>
        <p>&nbsp;</p>
        <p>
          I am fluent in Spanish, English (Cambridge Certificate of Advanced
          English - C1), and German (TestDaF - C1), which enables me to work
          effectively in multicultural and multilingual environments.
        </p>
        <p>&nbsp;</p>
        <p>
          Beyond my primary technical skills, I bring a diverse range of
          additional expertise in cinematography, 3D modeling, music production,
          and scuba diving, reflecting my passion for creativity and
          exploration.
        </p>
        <p>&nbsp;</p>
        <p>
          If you are interested in learning more about me, feel free to download
          my latest CV.&nbsp;&nbsp;<span
            ><a href="/CV2024.pdf" target="blank" download
              >(Download CV)</a
            ></span
          >
        </p>
        <p>&nbsp;</p>
      </div>
    </div>
    <div class="page--cont--C">
      <div class="bio--icons">
        <img src="../assets/icons/react.png" />
        <img src="../assets/icons/next.png" />
        <img src="../assets/icons/vue.png" />
        <img src="../assets/icons/nuxt.png" />
        <img src="../assets/icons/js.png" />
        <img src="../assets/icons/html.png" />
        <img src="../assets/icons/css.png" />
        <img src="../assets/icons/tailwind.png" />
        <img src="../assets/icons/git.png" />
        <img src="../assets/icons/linux.png" />
      </div>
    </div>
  </div>
</template>
<style>
.bio--image {
  width: 30%;
  max-width: 200px;
  float: right;
  opacity: 0.6;
  border-radius: 5px;
  margin: 0px 0px 20px 20px;
}

.bio--text {
  overflow: hidden;
}

.bio--text > p > span > a {
  color: #8ac926;
  text-decoration: none;
  transition: 500ms;
}
.bio--text > p > span > a:hover {
  font-weight: bold;
}
.bio--icons {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  align-items: center;
}

.bio--icons > img {
  margin: 10px;
  width: 30px;
  opacity: 0.7;
}
</style>
