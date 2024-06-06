<script>
export default {
  name: "Input"
}
</script>

<template>
  <div class="w-full h-full text-black">
    <div class="ml-4 bg-white relative top-2 px-2 inline w-auto z-10 max-md:ml-2">
      <slot name="title"></slot>
    </div>

    <div class="relative z-[5] flex items-center justify-between opacity-70 transition-opacity hover:opacity-100" v-if="$slots.options || $slots.required">
      <select v-if="$slots.required" class="select-required px-2">
        <slot name="required"></slot>
      </select>

      <select v-else class="select px-2">
        <slot name="options"></slot>
      </select>
    </div>

    <div v-if="$slots.date" class="date select flex items-center justify-between opacity-70 transition-opacity hover:opacity-100">
      <slot name="date"></slot>
      <input class="px-2 py-1" type="date" value="2024-06-01" />
    </div>

    <div v-if="$slots.input" class="select flex items-center justify-between opacity-70 transition-opacity hover:opacity-100">
      <slot name="input"></slot>
      <input class="px-2 py-1" type="text">
    </div>
  </div>
</template>