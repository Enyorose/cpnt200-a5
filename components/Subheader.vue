<template>
  <header>
    <h2 class="text-center text-3xl mt-2">{{ page.header }}</h2>
  </header>
</template>
<script>
export default {
  props: ["page"],
};
</script>