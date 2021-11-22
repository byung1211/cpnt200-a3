<template>
  <article>
    <nuxt-content :document="article" />
  </article>
</template>

<script>
  export default {
    async asyncData({ $content, params }) {
      console.log(params.slug)
      const article = await $content('articles', params.slug).fetch()

      return { article }
    }
  }
</script>