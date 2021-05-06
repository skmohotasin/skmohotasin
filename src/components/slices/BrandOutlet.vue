<template>
 <div class="row py-4 py-sm-2 py-md-3 py-lg-5 bc-Bg" :style="{ backgroundImage: 'url(' + slice.primary.background_image.url + ')'}">
    <div class="col-xxl-8 col-xl-8 col-lg-10 col-md-12 mx-auto text-center">
      <prismic-image :field="slice.primary.image" class="img-fluid"/>
    </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'brand-outlet'
}
</script>

<style scoped>
@media (min-width: 768px) {
  .bc-Bg {
    background-size: 100vw 55vh;
  }
}
@media (max-width: 767px) {
  .bc-Bg {
    background-size: 100vw 52vh;
  }
}
</style>