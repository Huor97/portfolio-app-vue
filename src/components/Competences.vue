<script setup lang="ts">
defineProps({
  competence: Object,
});
</script>

<template>
  <div class="max-sm:basis-1/2 max-sm:w-1/2">
    <div
      class="font-[montserrat] border-solid border-b-2 border-b-white-500 mb-2"
    >
      {{ competence?.titre }}
    </div>

    <div>
      <ul
        v-for="(technologye, index) in competence?.technology"
        :key="index"
        class="font-[montserrat] font-thin"
      >
        <li class="hover-2">{{ technologye }}</li>
      </ul>
    </div>
  </div>
</template>

<style></style>
