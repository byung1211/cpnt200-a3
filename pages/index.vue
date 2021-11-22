<template>
  <v-main>
    <v-container>
    <!-- <Tutorial/> -->
    <article>
      1. This header is from /components/cpnt200_header.vue
      <cpnt-200-header />
      <br />
      2. This is the link to the second page.<br />
      <NuxtLink to="/second">To Second page</NuxtLink><br />
      <NuxtLink to="/blog/my-first-blog-post">To first post in blog (Dynamic page)</NuxtLink><br />
      <NuxtLink to="/code-snippet/2021-11-21-this-is-a-code-snippet-from-the-conig-yml">To call without _slug (Test)</NuxtLink>
      <br />
      <br />
      3. This is from /content/home.md using the nuxt-content tag.
      <nuxt-content :document="page" />
      <br />
      4. This image optimized by the sizes attribute is from /static folder using the nuxt-img tag.
      <nuxt-img 
          src="/pexels-richard-verbeek-572861.jpg" 
          sizes="sm:100vw md:50vw lg:400px"/>
      <br />

      5. This title comes from a post for blog collection. <br />
      Title: {{ blog.title }}<br />
      
      6. This name comes from a profile for porfile collection. <br />
      Name: {{ profile.name }}<br />
      <img :src="profile.picture" alt="Alex-Byung UK An" />

      7. This title comes from a post for code snippet collection.<br />
      Title: {{ code.title }}<br />
    </article>
    <br /><br />
    8. This is a footer form the components folder.
    <Footer :copy="profile.name"/>
    </v-container>
  </v-main>
</template>
<style scoped>
a {
  color:blue;
  text-decoration:underline;
}

</style>
<script>
import cpnt200_header from '../components/cpnt200_header.vue'
export default {

  head() {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }],
    };
  },
  data() {
    return { 
      info: {
        title:'DATA TITLE TEST'
      }
    }
  },
  components: { cpnt200_header },
  async asyncData ({ $content }) {
    const page = await $content('home').fetch()
    const blog = await $content('blog/2021-11-21-this-is-a-test-post').fetch()
    const profile = await $content('profile/2021-11-22-this-is-the-first-profile').fetch()
    const code = await $content('code-snippet/2021-11-22-this-is-a-first-code-snippet').fetch()
    return {
      page, blog, profile, code
    }
  }
}
</script>
