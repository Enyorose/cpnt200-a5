<template>
  <header class="grid grid-cols-3 text-l text-center py-2 border-b-4 border-indigo-900">
    <div class="pt-4 px-2 text-left">HOME &gt; {{page.menuName.toUpperCase()}}</div>
    <div class="text-4xl font-bold">{{ page.header }}</div>
    <div class="pt-4 px-2 text-right"></div>
  </header>
</template>
<script>
export default {
  props: ["page"],
};
</script>