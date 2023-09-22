<script setup>
import { computed } from "@vue/reactivity";
import { ref } from "vue";
import TemplaTe from "@components/TemplaTe.vue";
import CompoNent from "./components/CompoNent.vue";

const valueTemplate = ref("");
const bo = ref("");
</script>

<template>
  <div>
    <TemplaTe @chek="(n) => (bo = n)" />

    <div v-show="bo">
      <h2>напищить количество</h2>
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
