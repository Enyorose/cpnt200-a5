<template>
<v-main>
  <v-container>
    <Header  :siteInfo="siteInfo" :pageInfo="pageInfo" />
    <section>
      <div class="text-center mt-8">
        <h2 class="text-3xl font-bold">Blog Post</h2>
      </div>
          <div class="mb-4">
            <h3 v-text="'Title: '+post.title" class="text-xl font-bold mb-2"></h3>
            <h4>- Date: {{post.date}}</h4>
            <h4>- Keywords: {{post.description}}</h4>
            <nuxt-content
              class="bg-gray-200 mt-2 mb-8 mx-4"
              :document="post"
            />
          </div>
    </section>
    <Footer :info="siteInfo" />
  </v-container>
</v-main>
</template>
<style scoped>
.container {
  padding-top: 0px !important;
}
</style>
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
        name: 'blog',
      }
    }
  },
  async asyncData({ $content, params }) {
    const siteInfo = await $content('site-info').fetch()
    const post = await $content('blog', params.slug).fetch()
    return { siteInfo, post }
  }
}
</script>