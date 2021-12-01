<template>
  <v-main>
    <Header :pageInfo="pageInfo" />
    <section class="mt-8 mx-10">
      <div class="flex justify-between content-end text-l text-center py-2 border-b-4 border-indigo-900">
        <h2 class="pt-4 px-2">HOME &gt; BLOG &gt; POSTING</h2>
        <h1 class="text-4xl font-bold pr-20 mr-10">Tech Postings</h1>
        <h2 class="pt-4 px-2"></h2>
      </div>
      <div class="p-10 grid grid-cols-1
          sm:grid-cols-1
          md:grid-cols-3
          lg:grid-cols-3
          xl:grid-cols-3
          gap-5">

        <!-- Card -->
        <div v-for="(post, index) in posts" :key="index" class="ounded overflow-hidden shadow-lg bg-gray-100 py-1 px-1">
          <NuxtLink :to="`/blog/${post.slug}`">
            <nuxt-img :src="post.image" :alt="post.title" class="w-full" />
          </NuxtLink>
          <div class="px-6 py-4">
            <div class="font-bold text-xl mb-2">
              <NuxtLink :to="`/blog/${post.slug}`">{{ post.title }}</NuxtLink>
            </div>
            <p v-text="post.description" class="text-gray-700 text-base"></p>
          </div>
          <div class="px-6 pt-4 pb-2">
            <span
              v-for="(tag, index) in post.tag.split('#')"
              :key="index"
              v-if="(tag !== null && tag !== '')"
              class="
                inline-block
                bg-yellow-200
                rounded-full
                px-3
                py-1
                text-sm
                font-semibold
                text-gray-700
                mr-2
                mb-2
              "
            >
              #{{ tag }}
            </span>
          </div>
        </div>
      </div>
    </section>

    <Footer />
  </v-main>
</template>
<style scoped>
.container {
  padding-top: 0px !important;
}
</style>
<script>
export default {
  data() {
    return {
      // Custom page data comes here.
      pageInfo: {
        menuName: "blog",
      },
    };
  },
  async asyncData({ $content }) {
    const posts = await $content("blog")
      .sortBy("createdAt", "desc")
      .fetch()
      .catch((err) => {
        error({ statusCode: 404, message: "Page not found" });
      });

    console.log(posts);

    return {
      posts,
    };
  },
  methods: {},
};
</script>
