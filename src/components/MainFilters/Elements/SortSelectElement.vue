<script>
export default {
  name: "SortSelect"
}
</script>

<template>
  <div class="flex items-center gap-2">
    <select class="text-blue-800 border-0 w-auto h-auto outline-none">
      <slot></slot>
    </select>
    <img class="h-2 rotate-90 mr-2" src="../../../assets/right-arrow.png" alt="">
  </div>
</template>