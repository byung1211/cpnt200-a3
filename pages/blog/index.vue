<template>
<v-main>
  <v-container>
    <Header  :info="siteInfo" />
    Blog page
    <Footer  :info="siteInfo" />
  </v-container>
</v-main>
</template>
<script>
export default {

  data() {
    return {
      // Custom page data comes here.
    }
  },
  async asyncData ({ $content }) {
    const siteInfo = await $content('site-info').fetch()
    return {
      siteInfo
    }
  }
}
</script>
