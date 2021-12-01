<template>
  <v-main>
    <Header :pageInfo="pageInfo" />
    <section class="mt-8 mx-10">
      <Subheader :page="pageInfo" />
      <article class="max-w-3xl mx-auto mt-4">
        <p class="text-base">
          Our team of developers are dedicated to bringing you the highest
          quality content on the most up to date technology. We do all the
          research and summarize it, so you can make the most informed choices
          for your own project.
        </p>
      </article>
      <article class="max-w-3xl mx-auto mt-5">
        <p class="text-base">
          Here is an opportunity to tell us what you would like to see next.
          Fill out this short form and keep an eye out we may cover your topic
          next!
        </p>
        <form
          @submit.prevent="addComment"
          class="mt-5 flex flex-col items-center border-2 max-w-md"
        >
          <InputComment
            :value="message.msg"
            :inputInfo="message"
            v-model="message.msg"
            class="border-0"
          />
          <button class="bg-gray-400 mt-5">Add Comment</button>
        </form>
        <ul>
          <li
            v-for="message in commentItems"
            :key="message.id"
            class="border-solid border-2 my-4"
          >
            <p>{{ message.msg }}</p>
          </li>
        </ul>
      </article>
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
export default {
  data() {
    return {
      // Custom page data comes here.
      pageInfo: {
        menuName: "about",
        header: "About Us",
      },
      message: {
        msg: "",
        label: "We are interested in your idea!",
        inputName: "input comment",
        comment: "",
      },
      commentItems: [],
    };
  },
  methods: {
    addComment: function () {
      console.log(this.message.msg);
      return this.commentItems.push({
        msg: this.message.msg,
      });
    },
  },
};
</script>
