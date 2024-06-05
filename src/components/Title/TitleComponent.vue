<script>
export default {
  name: "Title"
}
</script>

<template>
  <div class="flex items-center gap-10 justify-between max-md:gap-0">
    <div>
      <div class="text-2xl font-medium">Advanced search</div>
      <div class="text-sm text-red-600">Заполните обязательные поля*</div>
    </div>

    <div class="relative right-0 cursor-pointer opacity-60 transition-opacity w-4 flex items-center justify-center hover:opacity-100">
      <span class="block w-[2px] h-[20px] bg-black rounded-[20%] rotate-45"></span>
      <span class="block w-[2px] h-[20px] bg-black rounded-[20%] top-0 absolute -rotate-45"></span>
    </div>
  </div>
</template>