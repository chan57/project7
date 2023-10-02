<script setup>
import { ref } from "vue";

function func(event){
  alert(event)
}
const text = ref('');
const uslovie = ref(false);
const newText = ref('');
const znchenie = ref(false)
function send() {
  uslovie.value = true;
  newText.value = `new Massage: ${text.value}`
  if(text.value == '') uslovie.value = false
}
</script>

<template>
  <div>

    <h1>Home</h1>
    <br>
    <button @click="znchenie = !znchenie">write message</button>
    <div v-if="znchenie">
    <textarea @keydown.enter="send" v-model.trim="text"></textarea>
    <div v-if="uslovie">
      <h3>{{ newText }}</h3>
    </div>
    </div>

  </div>
</template>