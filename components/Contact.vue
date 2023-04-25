<template>
  <div class="page">
    <div class="page--cont--A">
      <p class="page--title">Contact</p>
    </div>
    <div class="page--cont--B">
      <div class="contact">
        <div
          class="contact--question page--subtitle"
          v-if="result != String(numberOne + numberTwo)"
        >
          <p>How much is {{ numberOne }} + {{ numberTwo }} ?</p>
          <input class="page--subtitle" v-model="result" />
          <br />
          <input class="honey" ref="honeyRef" type="text" />
        </div>
        <div
          class="contact--answer"
          v-if="result === String(numberOne + numberTwo) && honey === null"
        >
          <div class="contact--answer--icons--cont">
            <a :href="email" target="blank"
              ><img src="../assets/icons/email.png" />{{ email }}</a
            >
            <a :href="phone" target="blank"
              ><img src="../assets/icons/phone.png" />{{ phone }}</a
            >
            <a
              href="https://www.linkedin.com/in/jan-carlos-zemelka-537072194/"
              target="blank"
              ><img src="../assets/icons/linkedin.png" />Linkedin</a
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      numberOne: parseInt(Math.random() * 10),
      numberTwo: parseInt(Math.random() * 10),
      input: null,
      email: "zemelka270@gmail.com",
      phone: "+52 55 7370 1142",
      honey: null,
      result: null,
    };
  },
};
</script>
<style>
.honey {
  display: none;
}

.contact {
  padding: 20px;
}
.contact--question {
  text-align: center;
}

.contact--question > input {
  text-align: center;
  max-width: 120px;
  border-radius: 10px;
  border: 2px solid black;
  color: white;
  background: none;
  font-family: "titles";
  margin: 30px;
}

.contact--answer {
  text-align: center;
}

.contact--answer--icons--cont {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  width: 100%;
  height: 100%;
  justify-content: flex-start;
  align-items: flex-start;
}

.contact--answer--icons--cont > a {
  display: flex;
  justify-content: center;
  align-items: center;
  /* margin: 20px; */
  text-decoration: none;
  color: white;
  transition: 500ms;
}
.contact--answer--icons--cont > a:hover {
  font-weight: bold;
}

.contact--answer--icons--cont > a > img {
  width: 30px;
  padding: 20px;
}
</style>
