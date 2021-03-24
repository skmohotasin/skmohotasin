<template>
  <div class="row py-2 py-sm-2 py-md-3 py-lg-5">
    <div class="col-xxl-8 col-xl-12 col-lg-12 col-md-12 mx-auto text-center">
      <prismic-rich-text class="heading-custom-color pb-md-2 mb-2" :field="slice.primary.band_name"/>
      <prismic-rich-text class="title-custom-color mb-3 mb-md-4"  :field="slice.primary.title"/>
      <prismic-rich-text class="description mb-3 mb-md-4" :field="slice.primary.description_body"/>
      <template v-if="$prismic.richTextAsPlain(slice.primary.link_label) !== ''">
        <p class="pt-2 pt-md-3">
          <prismic-link  class="'btn btn-circle" :field="slice.primary.link">{{ $prismic.richTextAsPlain(slice.primary.link_label) }}</prismic-link>
        </p>
      </template>
    </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'description-slice'
}
</script>

<style scoped>
.btn-circle {
  text-decoration: none;
  color: #ff009c;
  border:2px solid #ff009c;
  border-radius: 48px;
  padding: 10px 20px;
}
.btn-circle:hover {
  color: #fff;
  border:2px solid #ff009c;
  background: #ff009c;
}
.heading-custom-color{
  color: #ff009c;
}
.title-custom-color{
  color:#5b146f;
}
.description {
  color: #464646;
}
@media (min-width: 1200px) {
    .btn-circle {
        padding: 15px 30px;
    }
}
</style>
