<script setup>
import MainFilters from "./components/MainFilters/MainFiltersComponent.vue";
import Apply from "./components/Apply/ApplyComponent.vue";
import Title from "./components/Title/TitleComponent.vue";
</script>

<template>
  <div class="container w-full p-3 max-w-full">
    <Title />
    <MainFilters />
    <Apply />
  </div>
</template>