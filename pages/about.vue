<template>
  <v-main>
   
    <Header :pageInfo="pageInfo"/>
    About page....
    <Footer />
    
  </v-main>
</template>
<style scoped>
  /*
   *  Custom styles for the page
   */
</style>
<script>
export default {

  data() {
    return {
      // Custom page data comes here.
      pageInfo: {
        menuName: 'about',
      }
    }
  },
  async asyncData ({ $content }) {

    return {
    }
  }
}
</script>
