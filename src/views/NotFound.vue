<template>
  <div>
    <!-- Vue tag to add header component -->
    <header-prismic/>
    <div class="container">
      <h1>Page not found</h1>
      <p>Site in progress...coming soon </p>
      
    </div>
  </div>
</template>

<script>
import HeaderPrismic from '../components/HeaderPrismic.vue'

export default {
  name: 'NotFound',
  components: {
    HeaderPrismic
  }
}
</script>
