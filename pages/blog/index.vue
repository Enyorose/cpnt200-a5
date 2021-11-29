<template>
  <v-main>
    <Header :pageInfo="pageInfo" />
    <section class="mt-8">
      <h1 class="text-3xl text-center font-bold">Tech Posts</h1>
      <div
        class="
          p-10
          grid grid-cols-1
          sm:grid-cols-1
          md:grid-cols-3
          lg:grid-cols-3
          xl:grid-cols-3
          gap-5
        "
      >
        <ul>
          <li v-for="(post, index) in posts" :key="index">
            <!-- Card -->
            <div class="rounded overflow-hidden shadow-lg">
              <nuxt-img :src="post.image" :alt="post.title" class="w-full" />
              <div class="px-6 py-4">
                <div class="font-bold text-xl mb-2">{{ post.title }}</div>
                <p
                  v-text="post.description"
                  class="text-gray-700 text-base"
                ></p>
              </div>
              <div class="px-6 pt-4 pb-2">
                <span
                  v-for="(tag, index) in post.tag.split('#')"
                  :key="index"
                  v-if="tag !== null && tag !== ''"
                  class="
                    inline-block
                    bg-gray-200
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
          </li>
        </ul>
      </div>
    </section>

    <!-- <section>
    <div class="text-center mt-8">
      <h2 class="text-3xl font-bold">Blog Posts</h2>
    </div>
    <ul>
      <li v-for="(post, index) in posts" :key="index">
        <div class="mb-4">
          <h3 class="text-xl font-bold mb-2"><NuxtLink :to="`/blog/${post.slug}`">{{index+1}}.  {{ post.title }}</NuxtLink></h3>
          <h4>- Date: {{post.date}}</h4>
          <h4>- Keywords: {{post.description}}</h4>
          <nuxt-content
            class="bg-gray-200 mt-2 mb-8 mx-4"
            :document="post"
          />
        </div>
      </li>
    </ul>
  </section> -->

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
