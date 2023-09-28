<script setup>
import { computed, reactive } from "@vue/reactivity";
import { ref } from "vue";

import Home from "./components/Home.vue";
import About from "./components/About.vue";
import Setting from "./components/Setting.vue";

const routes = {
  "/Home": Home,
  "/About": About,
  "/Setting": Setting,
};

const currentPath = ref(window.location.hash);

window.addEventListener("hashchange", () => {
  currentPath.value = window.location.hash;
});

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || "/"] || NotFound;
});
</script>

<template>
  <div>
    <div class="container">
      <nav class="navbar navbar-expand-lg bg-body-tertiary">
        <div class="container-fluid">
          <a class="navbar-brand" href="#/Home">Home</a>
          <a class="navbar-brand" href="#/About">About</a>
          <a class="navbar-brand" href="#/Setting">Setting</a>
        </div>
      </nav>
    </div>

    <component :is="currentView" />
  </div>
</template>

<style scoped>
.container {
  display: flex;
}

</style>
