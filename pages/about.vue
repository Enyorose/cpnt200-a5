<template>
  <v-main>
    <Header :pageInfo="pageInfo" />
    <Subheader :page="pageInfo" />
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
        menuName: "about",
        header: "About Us",
      },
    };
  },
};
</script>
