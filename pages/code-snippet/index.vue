<template>
<v-main>
  <v-container>
    <Header  :siteInfo="siteInfo" :pageInfo="pageInfo" />
    <section>
      <h2 text-xl text-center>Code Snippet List</h2>
      <ul>
        <li v-for="(post, index) in posts" :key="index">
          <div>
          <h3>{{index+1}}.  {{ post.title }}</h3>
          <p>{{post.code.code}}</p>
          <nuxt-content
            class="prose prose-sm sm:prose lg:prose-lg xl:prose-2xl mx-auto"
            :document="{body: post.code.code}"
          />
          </div>
        </li>
      </ul>
    </section>
    <Footer  :info="siteInfo" />
  </v-container>
</v-main>
</template>
<script>
export default {

  data() {
    return {
      // Custom page data comes here.
      pageInfo: {
        name: 'code',
      }
    }
  },
  async asyncData ({ $content }) {
    const siteInfo = await $content('site-info').fetch()
    const posts = await $content("code-snippet")
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
  }
}
</script>
