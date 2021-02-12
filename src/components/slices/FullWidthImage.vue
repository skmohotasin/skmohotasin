<template>
  <section class='full-width-image content-section'>
    <div class="image">
      <prismic-image :field="slice.primary.image"/>
      </div>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'image-caption-slice'
}
</script>


<style scoped>

/*Media Queries*/
@media (min-width: 320px) {
  .image {
  width:100%;
  }
}

</style>