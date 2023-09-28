<script setup>
function func(event){
  alert(event)
}

</script>

<template>
  <div>
    <h1>Home</h1>
    <button @click.once="func($event)">knopk</button>
  </div>
</template>