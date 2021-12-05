<template>
  <div class="rounded overflow-hidden shadow-lg">
    <img class="w-full" :src="card.image" alt="Mountain" />
    <div class="px-6 py-4">
      <h2 class="font-bold text-2xl mb-2">{{ card.title }}</h2>
      <h3 class="text-xl">{{ card.name }}</h3>
      <p class="text-base">
        {{ card.description }}
      </p>
    </div>
    <div v-if="!card.filter" class="hidden"></div>
    <div v-else class="px-6 pt-4 pb-2">
      <span class="filter">{{ card.filter[0] }}</span>
      <span class="filter">{{ card.filter[1] }}</span>
      <span class="filter">{{ card.filter[2] }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["card"],
};
</script>
<style lang="postcss" scoped>
.filter {
  @apply inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2;
}
</style>
