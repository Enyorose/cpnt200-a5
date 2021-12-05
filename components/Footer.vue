<template>
  <footer class="fixed bottom-0 w-screen">
    <div class="bg-gray-800 text-center py-1">
      <h4 class="text-white" v-html="copyright"></h4>
    </div>
  </footer>
</template>
<script>
export default {
  data() {
    return {
      // Custom page data comes here.
      copyright: "&copy; 2021 CPNT200-A5 Tech Blog",
    };
  },
};
</script>
