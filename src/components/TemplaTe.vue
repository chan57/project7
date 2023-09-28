<script setup>
import { computed } from "@vue/reactivity";
import { ref, watch } from "vue";

const emit = defineEmits(["chek"]);

const color = ref("red");
const bol = ref(false);
const massage = ref('вкл кнопочки')
watch(bol, (newBol) => {
  emit("chek", bol.value);
  return newBol == false
    ? document.documentElement.style.setProperty("--pagebackground", `${"red"}`)
    : document.documentElement.style.setProperty(
        "--pagebackground",
        `${"green"}`
      );
});
document.documentElement.style.setProperty(
  "--pagebackground",
  `${color.value}`
);
</script>

<template>
  <div>
    <h1>{{ massage }}</h1>
    <input type="checkbox" v-model="bol" />
    <h4 class="hh">{{ bol }}</h4>
  </div>
</template>

<style scoped>
:root {
  --pagebackground: green;
}

.hh {
  color: var(--pagebackground);
}
</style>
