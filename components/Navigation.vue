<template>
  <ul class="flex justify-end">
    <li class="mr-2">
      <NuxtLink to="/" :class="(pageInfo.menuName === 'home'?navClass.active:navClass.inactive)">Home</NuxtLink>
    </li>
    <li class="mr-2">
      <NuxtLink to="/blog" :class="(pageInfo.menuName === 'blog'?navClass.active:navClass.inactive)">Blog</NuxtLink>
    </li>
    <li class="mr-2">
      <NuxtLink to="/members" :class="(pageInfo.menuName === 'members'?navClass.active:navClass.inactive)">Members</NuxtLink>
    </li>
    <li class="mr-2">
      <NuxtLink to="/about" :class="(pageInfo.menuName === 'about'?navClass.active:navClass.inactive)">About</NuxtLink>
    </li>
  </ul>
</template>
<script>
export default {
  props: ['pageInfo'],
  data() {
    return {
      // Custom page data comes here.
      navClass:{
        active: "font-extrabold text-center block border-2 border-gray-300 rounded py-2 px-4 bg-gray-300 text-indigo-600",
        inactive:"font-semibold text-center block border-2 border-gray-300 rounded py-2 px-4 text-blue-300 hover:bg-yellow-100 hover:text-indigo-600",
      }
    }
  },
}
</script>
