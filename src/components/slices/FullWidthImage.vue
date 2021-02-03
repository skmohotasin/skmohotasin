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


@media (max-width: 320px) {
.image{
    padding-block-start: 0px;
    padding-top:0px;
    width:200px;
    align-content: center;
    padding-left: 65px;
}
}

</style>