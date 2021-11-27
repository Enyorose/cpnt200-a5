<template>
  <v-main>
    <v-container>
    
    <Header :pageInfo="pageInfo"/>
    About page....
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
