
<template>
  <div class="row">
    <template v-if="$prismic.richTextAsPlain(slice.primary.master_title) !== ''">
      <div class="col-xl-12 col-lg-12 col-md-12 mx-auto text-center">
        <prismic-rich-text :field="slice.primary.master_title" :class="'title-custom-color mb-3 mb-md-4'"/>
      </div>
    </template>
    <div class="position-relative col-xxl-12 col-xl-12 col-lg-12 col-md-12 col-sm-12 m-0 p-0 mx-auto text-center">
      <div class="gallery-item-inner">
        <prismic-image :field="slice.primary.image"  class="img-responsive"/>
        <template v-if="$prismic.richTextAsPlain(slice.primary.title) !== ''">
          <div class="gallery-item-text-area">
            <div class="gallery-item-desciption d-inline-block align-middle p-4 px-lg-5 m-0">
              <template v-if="$prismic.richTextAsPlain(slice.primary.title) !== ''">
                <div class="d-block title-custom-color"><prismic-rich-text :field="slice.primary.title"/></div>
              </template>
              <template v-if="$prismic.richTextAsPlain(slice.primary.subtitle) !== ''">
                <div class="d-block title-custom-color"><prismic-rich-text :field="slice.primary.subtitle"/></div>
              </template>
              <template v-if="$prismic.richTextAsPlain(slice.primary.label) !== ''">
                <div class="mt-4"><prismic-link :field="slice.primary.link" class="btn-circle">{{ $prismic.richTextAsPlain(slice.primary.label) }}</prismic-link></div>
              </template>
            </div>
          </div>
        </template>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ['slice'],
  name: 'full-width-image'
}
</script>
<style scoped>
.gallery-item {
  position: relative;
}
.gallery-item-text-area {
  right: 0;
  left: 0;
  bottom: 0;
  top: 0;
  opacity: 1;
  filter: alpha(opacity=100);
  -webkit-transition: all .2s ease;
  -o-transition: all .2s ease;
  transition: all .2s ease;
  position: absolute;
  text-align: center;
  background: transparent;
  margin: auto;
}
@media (min-width: 768px) {
  .gallery-item-text-area {
    right: 50%;
    text-align: left;
  }
}
.gallery-item-text-area:before {
    content: '';
    display: inline-block;
    height: 100%;
    vertical-align: middle;
    margin-right: 0
}

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
.title-custom-color{
  color:#5b146f;
}
</style>