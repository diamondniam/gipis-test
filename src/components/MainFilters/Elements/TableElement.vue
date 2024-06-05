<script>
export default {
  name: "Table"
}
</script>

<template>
  <div v-if="$slots.full" class="border px-1 py-2 w-full bg-black/[.1]">
    <slot name="full"></slot>
  </div>
  <div v-else class="border px-1 py-2 w-full">
    <slot></slot>
  </div>
</template>