<template>
 <v-main>

    <Header :pageInfo="pageInfo" />
    <section class="mt-8 mx-10 mb-20">
      <div class="grid grid-cols-3 text-l text-center py-2 border-b-4 border-indigo-900">
        <div class="pt-4 px-2 text-left">HOME &gt; BLOG &gt; POSTING</div>
        <div class="text-4xl font-bold">Tech Article</div>
        <div class="pt-4 px-2 text-right"><NuxtLink :to="`/blog`"> &lt; Back to List</NuxtLink></div>
      </div>
      <div class="flex flex-col content-center">
        <!-- Article Head -->
        <div class="border-b-2 border-indigo-900 mb-4">
          <h3 v-text="'Title: '+post.title" class="text-xl font-bold mt-2 ml-2"></h3>
          <h4 class="flex justify-between ml-2 mt-2 text-gray-600 font-bold">
            <div>
              Tags: <span v-for="(tag, index) in post.tag.split('#')"
                        :key="index"
                        v-if="(tag !== null && tag !== '')"
                        class="
                          inline-block
                          bg-gray-300
                          rounded-full
                          px-3
                          py-1/2
                          text-sm
                          font-semibold
                          text-gray-700
                          mr-2
                          mb-2
                        ">#{{ tag }}</span>
            </div>
            <span class="mr-2">Published Date: {{formatTime(post.date)}}</span>
          </h4>
        </div>
        <!-- Article Body -->
        <div class="w-1/5 mx-auto">
          <nuxt-img :src="post.image" :alt="post.title" class="w-full" />
        </div>
        <div class="bg-blue-200 rounded-xl p-5 mt-4">
          <h4 class="font-bold pb-2">Description</h4>
          <p class="font-serif">{{post.description}}</p>
        </div>
        <nuxt-content
          class="bg-gray-200 px-2 py-4 mt-5 rounded-xl"
          :document="post"
        />
      </div>
    </section>

    <Footer />
  </v-main>
</template>
<script>
export default {
  data() {
    return {
      // Custom page data comes here.
      pageInfo: {
        menuName: 'blog',
      }
    }
  },
  async asyncData({ $content, params }) {
    const post = await $content('blog', params.slug).fetch()
    return { post }
  },
  methods: {
    formatTime: function(str) {
      
      return (new Date(Date.parse(str))).toLocaleDateString('en-us', { year:"numeric", month:"short", day:"numeric"});
    }
  }
}
</script>