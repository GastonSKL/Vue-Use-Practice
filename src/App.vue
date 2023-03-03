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
          <transition name="fade-in" mode="out-in"> 
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

.fade-in-enter-active{
  animation: fadeIn .5s ;
}
.fade-in-leave-active{
  animation: fadeOut .5s  ;
}
@keyframes fadeIn {
  0% {
    opacity: 0;
    
  }
  100% {
    opacity: 1;
  }
}
@keyframes fadeOut {
  0% {
    opacity: 1;
    
  }
  100% {
    opacity: 0;
  }
}
</style>
