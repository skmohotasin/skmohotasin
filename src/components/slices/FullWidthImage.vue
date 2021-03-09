<template>
<div class="row pt-2 pt-sm-2 pt-md-3 pt-lg-5 margin-not-b">
  <div class="col-xl-12 col-lg-12 col-md-12 col-sm-12 m-0 p-0 text-center">
    <prismic-image :field="slice.primary.image"  class="img-responsive"/>
  </div>
</div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'image-caption-slice'
}
</script>
<style>
.margin-not-b {
  margin-bottom: -3rem;
}
</style>