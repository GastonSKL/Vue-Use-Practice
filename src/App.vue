<script setup>
import { useColorMode } from "@vueuse/core";

const colorMode = useColorMode();

const switchMode = () => {
  colorMode.value === "light"
    ? (colorMode.value = "dark")
    : (colorMode.value = "light");
};
</script>

<template>
  <main>
    <div class="container">
      <div class="container__title">
        <h1>Dark a Light mode testing</h1>
      </div>
      <div class="container__description">
        <p>
          This test was made using the
          <span class="vueUse">VueUse</span> library on
          <span class="vue3">Vue 3</span>
        </p>
      </div>
      <div class="container__button">
        <button @click="switchMode">Switch</button>
      </div>
    </div>
  </main>
</template>

<style scoped>
main {
  height: 100vh;
}
.container {
  width: 50%;
  height: 100%;
  margin: auto;
  text-align: center;
  padding: 2em;
}

.container__title{
  margin-top: 5em;
}

.container__title h1{
  letter-spacing: .05em;
}

.container__description{
  margin-top: 6em;
  color: rgba(34, 34, 34, 0.699);
}

.container__description p{
  letter-spacing: .2em;
}

.vueUse{
  color: darkgreen;
  font-weight: bolder;
}

.vue3{
  color: green;
  font-weight: bolder;

}

.container__button{
  margin-top: 14em;
}


</style>
