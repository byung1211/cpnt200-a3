<template>
<v-main>
  <v-container>
    <Header  :siteInfo="siteInfo" :pageInfo="pageInfo" />
    <section>
      <h2 text-xl text-center>Blog Posts</h2>
      <ul>
        <li v-for="(post, index) in posts" :key="index">
        {{ index+1 }}.  {{ post.title }}
        </li>
      </ul>
    </section>
    <Footer :info="siteInfo" />
  </v-container>
</v-main>
</template>
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
  async asyncData ({ $content }) {
    const siteInfo = await $content('site-info').fetch()
    const posts = await $content("blog")
      .sortBy("createdAt", "desc")
      // .only(["title", "path"])
      .fetch()
      .catch((err) => {
        error({ statusCode: 404, message: "Page not found" });
      });

    console.log(posts)

    return {
      siteInfo, posts
    }
  },
  methods: {
    onLoad() {
      alert('test');
    }
  }
}
</script>
