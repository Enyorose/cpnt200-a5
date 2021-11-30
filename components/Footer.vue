<template>
  <footer class="border-t border-gray-200 my-2">
    <div
      class="container flex flex-wrap items-center justify-center py-2 mx-auto"
    >
      <h4 v-html="copyright"></h4>
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
