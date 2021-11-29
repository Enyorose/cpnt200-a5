<template>
  <v-main>

    <Header :pageInfo="pageInfo"/>
    <div>Techs Alot of the Round Table</div>
    <div>Big Header Photo Here</div>
    <div>Most Popular Content Here????</div>
    
    <Footer />

  </v-main>
</template>
<style scoped>
  /*
   *  Custom styles for the page
   */
</style>
<script>
import cnavigation from '../components/Navigation.vue'
import cheader from '../components/Header.vue'
import cfooter from '../components/Footer.vue'

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
        menuName: 'home',
      }
    }
  },
  components:{
    cnavigation, cheader, cfooter
  },  
  async asyncData ({ $content }) {

    return {
    }
  }
}
</script>
