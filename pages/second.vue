<template>
  <v-main>
    <v-container>
    <Navigation />
    <Header />
    <article>
      <br />
      2. This is the link to the home page.<br />
      <NuxtLink to="/">To Home page</NuxtLink>
      
    </article>
    </v-container>
  </v-main>
</template>
<style scoped>
a {
  color:blue;
  text-decoration:underline;
}
.nuxt-content-container {
  color:green;
}
</style>
<script>
import cpnt200_header from '../components/Header.vue'
export default {
  components: { cpnt200_header }
}
</script>
