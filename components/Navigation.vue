<template>
  <div class="container">
    <ul class="flex">
      <li class="flex-1 mr-2">
        <NuxtLink to="/" class="text-center block border border-blue-500 rounded py-2 px-4 bg-blue-500 text-white">
          Home
        </NuxtLink>
      </li>
      <li class="flex-1 mr-2">
        <NuxtLink to="/blog" class="text-center block border border-white rounded text-blue-500 hover:bg-gray-200 py-2 px-4">
          Blog
        </NuxtLink>
      </li>
      <li class="flex-1 mr-2">
        <NuxtLink to="/profile" class="text-center block border border-white rounded text-blue-500 hover:bg-gray-200 py-2 px-4">
          Profile
        </NuxtLink>
      </li>
      <li class="flex-1 mr-2">
        <NuxtLink to="/code-snippet" class="text-center block border border-white rounded text-blue-500 hover:bg-gray-200 py-2 px-4">
          Code Snippet
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>
<script>
export default {}
</script>
