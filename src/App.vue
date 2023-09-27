<script setup>
import { computed, reactive } from "@vue/reactivity";
import { ref } from "vue";

import Home from './components/Home.vue';
import About from './components/About.vue';
import Setting from "./components/Setting.vue"


const routes = {
  '/Home': Home,
  '/About': About,
  "/Setting": Setting
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/'] || NotFound
})

</script>

<template>
 <div>
<a href="#/Home">Home</a> |
<a href="#/About">About</a> |
<a href="#/Setting">Setting</a>
<component :is="currentView" />


</div>

</template>

<style>
</style>
