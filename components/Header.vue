<template>
  <header class="flex justify-between content-center bg-gray-800 py-5 px-5">
    <div class="text-white text-3xl whitespace-nowrap pt-1">
      <NuxtLink to="/"><i class="fab fa-watchman-monitoring"></i> {{siteName}}</NuxtLink>
    </div>
    <Navigation :pageInfo="pageInfo" />
  </header>
</template>
<script>
export default {
  props: ['pageInfo'],
  data() {
    return {
  
      // Custom page data comes here.
      siteName: "CPNT200-A5 Tech Blog",
    }
  }
}
</script>
