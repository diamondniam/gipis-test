<script>
import ButtonMain from "./ButtonElement.vue";

export default {
  name: "Apply",
  components: {ButtonMain}
}
</script>

<template>
  <div class="flex justify-center items-center mt-6 pt-4 border-t max-md:flex-col">
    <ButtonMain>Применить фильтр</ButtonMain>
    <div class="mt-2 text-red-600 absolute cursor-pointer right-2 max-md:static">Сбросить фильтр</div>
  </div>
</template>