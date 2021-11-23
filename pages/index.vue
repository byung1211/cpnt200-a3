<template>
  <v-main>
    <v-container>
    <Header />

    <section>
      <br/><br/><br/>
      Intro content area
      <br/><br/><br/>
    </section>
    <Footer :copyright="siteInfo.copyright"/>
    </v-container>
  </v-main>
</template>
<style scoped>

</style>
<script>

import cnavigation from '../components/Navigation.vue'
import cheader from '../components/Header.vue'
import cfooter from '../components/Footer.vue'

export default {

  head() {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }],
    };
  },
  data() {
    return { 
      siteInfo: {
        title:'DATA TITLE TEST',
        copyright: '2021 Alex-Byung Uk An, SAIT WEB DEV PROGRAM'
      }
    }
  },
  components:{
    cnavigation, cheader, cfooter
  },  
  async asyncData ({ $content }) {
    const introInfo = await $content('intro').fetch()
    return {
      introInfo
    }
  }
}
</script>
