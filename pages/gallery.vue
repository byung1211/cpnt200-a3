<template>
  <v-main>
    <v-container>
      <Navigation />
      <Header />
      <article>
        This is the link to the home page.<br />
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
import cnavigation from '../components/Navigation.vue'
import cheader from '../components/Header.vue'
import cfooter from '../components/Footer.vue'

export default {
  components:{
    cnavigation, cheader, cfooter
  }
}
</script>
