<template>
  <header class="bg-indigo-100 py-3 px-4">
    <div class="container flex flex-wrap items-center justify-center py-3 mx-auto">
      <h1 class="text-3xl md:text-4xl font-medium mb-2text-3xl md:text-4xl font-medium mb-2">{{info.title}}</h1>
    </div>
    <Navigation />
  </header>
</template>
<style scoped>
</style>
<script>
export default {
  props: ['info']
}
</script>

