<template>
   <div class="row py-2 py-sm-2 py-md-3 py-lg-5">
    <div class="col-xxl-8 col-xl-8 col-lg-10 col-md-12 mx-auto text-center">
      <prismic-rich-text class="h5 heading-custom-color" :field="slice.primary.text"/>
      <prismic-rich-text class="custom-color h1 fw-bold pb-md-2" :field="slice.primary.testing"/>
      <prismic-rich-text class="description fw-light" :field="slice.primary.headline"/>
    </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'description-link'
}
</script>

<style scoped>
.btn-circle {
  color: #ff009c;
  border:2px solid #ff009c;
  border-radius: 48px;
  padding: 10px 20px;
}
.btn-circle:hover {
  color: #fff;
  border:2px solid #fff;
  background: #ff009c;
}
.custom-color{
  color:#5b146f;
}
.heading-custom-color{
  color: #ff009c;
}
</style>
