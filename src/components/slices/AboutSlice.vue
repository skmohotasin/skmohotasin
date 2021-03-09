<template>
    <div class="row py-2 py-sm-2 py-md-3 py-lg-5">
      <div class="col-xl-8 col-lg-10 col-md-10 mx-auto text-center">
        <div class="row d-flex align-items-center justify-content-center">
          <div class="col-xl-6 col-lg-6 col-md-6 col-sm-12 py-2 py-md-0 mx-auto text-center">
            <prismic-image :field="slice.primary.featured_image" class="img-responsive"/>
          </div>
          <div class="col-xl-6 col-lg-6 col-md-6 col-sm-12 py-2 py-md-0 mx-auto text-center">
              <prismic-rich-text class="h5 heading-custom-color" :field="slice.primary.text"/>
              <prismic-rich-text class="custom-color h1 fw-bold pb-md-2" :field="slice.primary.testing"/>
              <prismic-rich-text class="description fw-light" :field="slice.primary.headline"/>
              <p class="pt-2 pt-md-3">
                <prismic-link  class="btn btn-circle" :field="slice.primary.link">{{ $prismic.richTextAsPlain(slice.primary.link_label) }}</prismic-link>
              </p>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'about-slice'
}
</script>

<style scoped>
.btn-circle {
  color: #5b146f;
  border:2px solid #5b146f;
  border-radius: 48px;
  padding: 10px 100px;
}
.btn-circle:hover {
  color: #fff;
  border:2px solid #fff;
  background: #5b146f;
}
.custom-color{
  color:#5b146f;
}
.heading-custom-color{
  color: #ff009c;
}
</style>