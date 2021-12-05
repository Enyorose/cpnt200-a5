<template>
  <v-main>

    <Header :pageInfo="pageInfo"/>
    <section>
      <div class="text-center mt-10">
        <h1 class="text-3xl font-bold">We deal with Everything in Network.</h1>
      </div>
      <div class="w-1/2 mt-8 mx-auto">
        <nuxt-img src="/image/network-782707.png" alt="network" class="w-full" />
      </div>
      <div class="text-center mt-10 mx-auto w-2/3">
        <p class="text-xl font-sans font-semibold">
        The speed and scope of the transformation of our communication environment by Internet and wireless communication has triggered all kind of utopian and dystopian perceptions around the world.
        </p>
      </div>
    </section>
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
