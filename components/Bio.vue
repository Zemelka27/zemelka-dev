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
          I am a front-end developer based in Germany and Mexico, I've been
          working for several companies in this capacity since 2020.
        </p>
        <p>&nbsp;</p>
        <p>
          I hold a Bachelor of Engineering in Audiovisual Media from Hochschule
          der Medien in Stuttgart and an Erasmus one-year program in a Bachelor
          of Science in Audiovisual Communication from Universidad Rey Juan
          Carlos in Madrid. To update my academic formation I have completed
          various front-end courses from Udemy and Scrimba.
        </p>
        <p>&nbsp;</p>
        <p>
          I am proficient in technologies such as React, Vue.js, Nuxt.js, and
          Node.js, as well as HTML, CSS. I also have experience using headless
          content management systems such as Strapi, Contentful and Netlify CMS.
        </p>
        <p>&nbsp;</p>
        <p>
          In addition, I am fluent in Spanish, English (Cambridge’s Certificate
          of Advanced English - C1), and German (TestDaF - C1).
        </p>
        <p>&nbsp;</p>
        <p>
          Lastly, I have several side skills in fields like cinematography, 3D,
          music, and scuba diving.
        </p>
        <p>&nbsp;</p>
        <p>
          If you are interested in learning more about me, feel free to download
          my latest CV.&nbsp;&nbsp;<span
            ><a href="../assets/downloads/CV2023.pdf" download
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
        <img src="../assets/icons/vue.png" />
        <img src="../assets/icons/nuxt.png" />
        <img src="../assets/icons/ts.png" />
        <img src="../assets/icons/js.png" />
        <img src="../assets/icons/html.png" />
        <img src="../assets/icons/css.png" />
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
  color: greenyellow;
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
  opacity: 0.6;
}
</style>
