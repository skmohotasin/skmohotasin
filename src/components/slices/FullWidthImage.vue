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


@media (max-width: 320px) 
and (max-device-width: 480px)
  {

.image{
  width: 320px;
  align-items: left;
  padding-bottom: 0px;
  padding-left: 0px;
  padding-right: 0px;
}
}

</style>