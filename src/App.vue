<script setup>
import { computed, reactive } from "@vue/reactivity";
import { ref } from "vue";
import TemplaTe from "@components/TemplaTe.vue";
import CompoNent from "./components/CompoNent.vue";

const valueTemplate = ref("");
const bo = ref("");
const color = ref("");
const setColor = reactive(["blue", "green", "red", "yellow", "black"]);
let numb = ref("");
const change = function () {
  numb = Math.trunc(Math.random() * 5) - 1;
  color.value = setColor[numb];
};
const changeColor = function () {
  change();
  if (color.value == setColor[numb]) {
    change();
  }
};
</script>

<template>
  <div>
    <TemplaTe @chek="(n) => (bo = n)" />

    <div v-show="bo">
      <h2 :style="{ color: color }">напищить количество</h2>
      <button @click="changeColor">change color</button>
      <input v-model.trim.number="valueTemplate" />
      <button v-on:click="valueTemplate = ''">delete</button>

      <h3>{{ valueTemplate }}</h3>

      <div v-show="valueTemplate">
        <div v-for="i of valueTemplate" v-bind:key="i">
          <CompoNent />
        </div>
      </div>
    </div>
  </div>
</template>

<style>
</style>
