<template>
  <v-main>
    <v-container>
    
    <Header :pageInfo="pageInfo"/>
    <Card :card="cardInfo"/>
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
        menuName: 'members',
      },
      cardInfo: {
        name: 'Jessica Watson',
        title: 'Backend',
        description: 'Set up and managed server information as well as designed members page.',
        filter: ['#family', '#photographer', '#developer']
      }
    }
  },
  
}
</script>
