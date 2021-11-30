<template>
  <header class="flex justify-between content-end text-l text-center py-2 border-b-4 border-indigo-900">
    <h2 class="pt-4 px-2">HOME &gt; BLOG &gt; {{page.menuName.toUpperCase()}}</h2>
    <h1 class="text-4xl font-bold pr-20 mr-20">{{ page.header }}</h1>
    <h2 class="pt-4 px-2"></h2>
  </header>
</template>
<script>
export default {
  props: ["page"],
};
</script>