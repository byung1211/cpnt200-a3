<template>
  <!-- <Tutorial/> -->
  <article>
    1. This header is from /components/cpnt200_header.vue
    <cpnt-200-header />
    <br />
    2. This is the link to the home page.<br />
    <NuxtLink to="/">To Home page</NuxtLink>
    
  </article>
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
import cpnt200_header from '../components/cpnt200_header.vue'
export default {
  components: { cpnt200_header }
}
</script>
