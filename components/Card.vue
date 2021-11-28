<template>
    <div class="p-10 grid grid-cols-1 sm:grid-cols-1 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-4 gap-5">
        <div class="rounded overflow-hidden shadow-lg">
      <img class="w-full" src="/mountain.jpg" alt="Mountain">
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">Mountain</div>
        <p class="text-gray-700 text-base">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, Nonea! Maiores et perferendis eaque, exercitationem praesentium nihil.
        </p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <span class="filter">#photography</span>
        <span class="filter">#travel</span>
        <span class="filter">#winter</span>
      </div>
     </div>
    </div> 
</template>

<script>
export default {
    props: ['card']
}
</script>
<style lang="postcss" scoped>
.filter {
    @apply inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2
}
</style>
