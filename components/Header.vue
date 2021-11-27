<template>
  <header class="flex bg-indigo-900 py-3">
    <h1 class="text-white text-2xl whitespace-nowrap">{{siteName}}</h1><Navigation :pageInfo="pageInfo" />
  </header>
</template>
<script>
export default {
  props: ['pageInfo'],
  data() {
    return {
  
      // Custom page data comes here.
      siteName: "CPNT200-A5-Final Project",
    }
  }
}
</script>
