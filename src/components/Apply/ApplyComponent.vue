<script>
import ButtonMain from "./ButtonElement.vue";

export default {
  name: "Apply",
  components: {ButtonMain}
}
</script>

<script setup>
import {onMounted, ref} from "vue";

let checkForRequired = ref(null)
let clearFilters = ref(null)

onMounted(() => {
  const required = document.querySelectorAll(".select-required");
  const allSelect = document.querySelectorAll("select, input, .circle");

  checkForRequired = () => {
    let isSelected = true

    required.forEach(select => {
      if (select.value === '0') {
        isSelected = false
      }
    })

    if (!isSelected) {
      return alert('Select required!')
    } else {
      return alert('Success!')
    }
  }

  clearFilters = () => {
    allSelect.forEach(select => {
      if (select.tagName === 'SELECT') {
        select.value = '0'
      } else if (select.tagName === 'INPUT') {
        select.value = ''
      } else {
        select.classList.remove('selected')
      }
    })
  }
})
</script>

<template>
  <div class="flex justify-center items-center mt-6 pt-4 border-t max-md:flex-col">
    <ButtonMain @click="checkForRequired()">Применить фильтр</ButtonMain>
    <div @click="clearFilters()" class="mt-2 text-red-600 absolute cursor-pointer right-2 max-md:static">Сбросить фильтр</div>
  </div>
</template>