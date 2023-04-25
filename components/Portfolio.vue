<template>
  <div class="page">
    <div class="page--cont--A">
      <p class="page--title">Portfolio</p>
    </div>
    <div class="page--cont--B">
      <ul>
        <li>
          <p class="page--subtitle">Cicada Securities, LLC (FE Challenge)</p>
          <p>
            <span class="page--subtitle--span">Description: </span>
            React app intended for currency trading.
          </p>
          <span class="page--subtitle--span">Link: </span>
          <a
            href="https://github.com/Zemelka27/cicada-react-fe-challenge-2022"
            target="blank"
          >
            https://github.com/Zemelka27/cicada-react-fe-challenge-2022</a
          >
        </li>
        <li>
          <p class="page--subtitle">Simplicita</p>
          <p>
            <span class="page--subtitle--span">Description: </span>
            Licitation services website created in Vue.js with backend on AWS
          </p>
          <span class="page--subtitle--span">Link: </span>
          <a href="https://simplicita.netlify.app" target="blank">
            https://simplicita.netlify.app/</a
          >
        </li>
        <!-- <li>
          <p class="page--subtitle">Salaer GmbH</p>
          <p>
            <span class="page--subtitle--span">Description: </span>
            Online store created with Nuxt.js framework with integration of
            SnipCart and Google Tags
          </p>
          <span class="page--subtitle--span">Link: </span>
          <a href="https://abeck-und-dr-med-walter.netlify.app/" target="blank">
            https://abeck-und-dr-med-walter.netlify.app/</a
          >
        </li> -->
        <li>
          <p class="page--subtitle">Praxis A. Beck & Dr. med. E. Walter</p>
          <p>
            <span class="page--subtitle--span">Description: </span>
            Medical laboratory website created with Nuxt.js framework and
            integration of Netlify Headless CMS
          </p>
          <span class="page--subtitle--span">Link: </span>
          <a href="https://abeck-und-dr-med-walter.netlify.app/" target="blank">
            https://abeck-und-dr-med-walter.netlify.app/</a
          >
        </li>
        <li>
          <p class="page--subtitle">Alexander F. Beck</p>
          <p>
            <span class="page--subtitle--span">Description: </span>
            Photographer portfolio created with Nuxt.js framework.
          </p>
          <span class="page--subtitle--span">Link: </span>
          <a href="https://www.afbeck-photography.com" target="blank">
            https://www.afbeck-photography.com</a
          >
        </li>
      </ul>
    </div>
  </div>
</template>

<style>
ul {
  padding: 0;
  list-style-type: none;
}

li {
  padding-bottom: 20px;
}

li > p {
  padding-bottom: 5px;
}

li > a {
  text-decoration: none;
  color: #1982c4;
  transition: 500ms;
}

li > a:hover {
  font-weight: bold;
}
</style>
