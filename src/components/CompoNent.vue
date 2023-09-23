<script setup>
import { ref } from "vue";

const mes = ref("mes");
</script>

<template>
  <div>
    <nav class="navbar bg-body-tertiary">
      <form class="container-fluid justify-content-start">
        <button class="btn btn-outline-success me-2" type="button">
          маленька кнопчк
        </button>
        <button class="btn btn-sm btn-outline-secondary" type="button">
          большая кнопчк
        </button>
      </form>
    </nav>
  </div>
</template>

<style scoped>
</style>