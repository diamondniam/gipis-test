<script>
export default {
  name: "ButtonSelect"
}
</script>

<script setup>
import {onMounted} from "vue";

onMounted(() => {
  const buttons = document.querySelectorAll("#button-select");

  function removeSelected() {
    buttons.forEach((button) => {
      button.querySelector('.circle').classList.remove("selected");
    })
  }

  buttons.forEach(button => {
    button.onclick = () => {
      removeSelected()
      button.querySelector('.circle').classList.toggle('selected')
    }
  })
})
</script>

<template>
  <div id="button-select" class="group cursor-pointer flex items-center gap-2">
    <div class="flex justify-center w-4 h-4 rounded-2xl bg-blue-900">
      <div class="circle border-2 border-white rounded-3xl w-4 m-0.5 bg-white transition-background duration-200"></div>
    </div>
    <slot></slot>
  </div>
</template>

<style>
.selected {
  @apply bg-blue-900;
}
</style>