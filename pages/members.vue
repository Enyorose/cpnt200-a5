<template>
  <v-main>
    <Header :pageInfo="pageInfo" />
    <div
      class="
        p-10
        grid grid-cols-1
        sm:grid-cols-1
        md:grid-cols-3
        lg:grid-cols-4
        xl:grid-cols-4
        gap-5
      "
    >
      <Card :card="card" v-for="card in cards" :key="card.id" />
    </div>
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
        menuName: "members",
      },
      cards: [
        {
          name: "Devon",
          title: "Design",
          description:
            "Came up with the figma design and color scheme as well as helped edit the content.",
          image: "images/devon.jpg",
        },
        {
          name: "Hyeju",
          title: "Content",
          description: "Researched and wrote the blog entries.",
          image: "images/hyeju.jpg",
        },
        {
          name: "Jessica",
          title: "Backend",
          description:
            "Set up and managed server information as well as designed members page.",
          image: "images/jessica.jpg",
        },
        {
          name: "Alex",
          title: "Frontend",
          description:
            "Created components and styled a lot of the dynamic pages.",
          image: "images/alex.png",
        },
      ],
    };
  },
};
</script>
