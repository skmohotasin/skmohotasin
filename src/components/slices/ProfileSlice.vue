<template>
    <div class="row">
      <div class="col-xxl-12 col-xl-12 col-lg-12 col-md-12 mx-auto text-center gallery">
        <div class="row">
          <template v-if="$prismic.richTextAsPlain(slice.primary.title) !== ''">
            <div class="col-xl-12 col-lg-12 col-md-12 mx-auto text-center">
              <prismic-rich-text :field="slice.primary.title" :class="'title-custom-color mb-3 mb-md-4 mb-xl-5'"/>
            </div>
          </template>
          <template v-for="(item,index) in slice.items">
            <div :key="item.id" :class="'col-xl-4 col-lg-4 col-md-6 col-xs-12 mb-4 mb-md-0 mx-auto px-0 text-center gallery-item item-'+ index">
              <div class="gallery-item-inner">
                <prismic-image :field="item.main_image" class="img-responsive"/>
                  <div class="gallery-item-text-area">
                    <div class="gallery-item-desciption d-inline-block align-middle text-white p-4 m-0">
                      <div class="d-block"><prismic-rich-text :field="item.image_title"/></div>
                      <div class="d-block"><prismic-rich-text :field="item.image_description"/></div>
                        <template v-if="$prismic.richTextAsPlain(item.label) !== ''">
                          <div class="mt-4"><prismic-link :field="item.link" class="btn-circle">{{ $prismic.richTextAsPlain(item.label) }}</prismic-link></div>
                        </template>
                      </div>
                  </div>
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
  name: 'profile-slice'
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
  opacity: 0;
  filter: alpha(opacity=0);
  -webkit-transition: all .2s ease;
  -o-transition: all .2s ease;
  transition: all .2s ease;
  position: absolute;
  text-align: center;
  background:linear-gradient(to top left, #ff009c,#00a9ff);
  margin: auto;
}
.gallery-item-text-area:before {
    content: '';
    display: inline-block;
    height: 100%;
    vertical-align: middle;
    margin-right: 0
}

.gallery-item-inner:hover .gallery-item-text-area {
    opacity: 1;
    filter: alpha(opacity=100)
}

.btn-circle {
  text-decoration: none;
  color: #fff;
  border:2px solid #fff;
  border-radius: 48px;
  padding: 10px 20px;
}
.btn-circle:hover {
  color: #fff;
  border:2px solid #5b146f;
  background: #5b146f;
}
.title-custom-color{
  color:#5b146f;
}
</style>