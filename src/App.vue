<script setup>
import { useColorMode } from "@vueuse/core";
import MoonButton from "./components/Moon.vue";
import SunButton from "./components/Sun.vue";
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
          <transition name="bounce-in" mode="out-in"> 
            <button @click="switchMode" v-if="colorMode==='light'" class="bounce-in-enter">
              <MoonButton />
            </button>
            <button @click="switchMode" v-else class="bounce-in-leave-to">
              <SunButton/>
            </button>
          </transition>
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

.container__title {
  margin-top: 5em;
}

.container__title h1 {
  letter-spacing: 0.05em;
}

.container__description {
  margin-top: 6em;
  color: rgba(34, 34, 34, 0.699);
}

.container__description p {
  letter-spacing: 0.2em;
}

.vueUse {
  color: darkgreen;
  font-weight: bolder;
}

.vue3 {
  color: green;
  font-weight: bolder;
}

.container__button {
  margin-top: 14em;
}

.bounce-in-enter-active {
  animation-name: bounce-in;
  animation-duration: 0.25s;
}

.bounce-in-leave-active {
  animation-name: bounce-in;
  animation-duration: 0.25s;
  animation-direction: reverse;
}

@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.2);
  }
  100% {
    transform: scale(1);
  }
}
</style>
