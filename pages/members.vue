<template>
  <v-main>
    <v-container>
    
    <Header :pageInfo="pageInfo"/>
    Members page....    
    <Footer />
    
    </v-container>
  </v-main>
</template>
<style scoped>
  /*
   *  Custom styles for the page
   */
</style>
<script>
export default {

  head() {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }],
    };
  },
  data() {
    return {
      // Custom page data comes here.
      pageInfo: {
        menuName: 'members',
      }
    }
  },
  async asyncData ({ $content }) {

    return {
    }
  }
}
</script>
