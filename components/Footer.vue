<template>
  <footer>
    <p> &copy; {{copy}} </p>
  </footer>
</template>
<style scoped>
  footer { 
    color:blue; 
    font-size:2rem;
  }
</style>
<script>
export default {
  props: ['copy']
}
</script>
