<script>
import Input from "@/components/MainFilters/Elements/BasicInputElement.vue";

export default {
  name: "Block",
  components: {Input}
}
</script>

<template>
  <div class="block">
    <div v-if="$slots.name" class="text-l font-medium min-w-24">
      <slot name="name"></slot>
    </div>
    <slot></slot>
  </div>
</template>