<template>
    <div class="row">
      <div class="col-xxl-12 col-xl-12 col-lg-12 col-md-12 mx-auto text-center gallery">
        <div class="row">
          <template v-if="$prismic.richTextAsPlain(slice.primary.gallery_title) !== ''">
            <div class="col-xl-12 col-lg-12 col-md-12 mx-auto text-center">
              <prismic-rich-text :field="slice.primary.gallery_title" :class="'title pb-4'"/>
            </div>
          </template>
          <template v-for="(item,index) in slice.items">
              <template v-if="index <= 2">
                <div v-bind:class="'col-xl-' + (12/slice.items.length) + ' col-lg-' + (12/slice.items.length) + ' col-md-6 col-xs-12 mb-4 mb-md-0 mx-auto px-0 text-center gallery-item item-'+ index" :key="item.id + value">
                  <div class="gallery-item-inner">
                    <prismic-image :field="item.image" class="img-responsive"/>
                      <div class="gallery-item-text-area">
                        <div class="gallery-item-desciption d-inline-block align-middle text-white p-4 m-0">
                          <div class="d-block mb-4"><prismic-rich-text :field="item.image_description"/></div>
                           <template v-if="$prismic.richTextAsPlain(item.link_label) !== ''">
                            <prismic-link :field="item.link" class="btn-circle">{{ $prismic.richTextAsPlain(item.link_label) }}</prismic-link>
                           </template>
                          </div>
                      </div>
                  </div>
                </div>
              </template>
              <template v-else-if="index >= 3">
                <div v-bind:class="'col-xl-' + (12/slice.items.length) + ' col-lg-' + (12/slice.items.length) + ' col-md-6 col-xs-12 mb-4 mb-md-0 mx-auto px-0 text-center gallery-item item-'+ index" :key="item.id">
                  <div class="gallery-item-inner">
                    <prismic-image :field="item.image" class="img-responsive"/>
                      <div class="gallery-item-text-area">
                        <div class="gallery-item-desciption d-inline-block align-middle text-white p-4 m-0">
                          <div class="d-block mb-4"><prismic-rich-text :field="item.image_description"/></div>
                            <template v-if="$prismic.richTextAsPlain(item.link_label) !== ''">
                            <prismic-link :field="item.link" class="btn-circle">{{ $prismic.richTextAsPlain(item.link_label) }}</prismic-link>
                            </template>
                          </div>
                      </div>
                  </div>
                </div>
              </template>
            </template>
        </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ['slice'],
  name: 'approach-slice'
}

// function imageresize(target) {
//     var width = target.offsetWidth / 1.2;
//     console.log(target.children[0].height, width);
//     target.children[0].height = width;
// }
// window.addEventListener('load', (event) => {
//     var target = document.querySelectorAll(".width-detect") ? document.querySelectorAll(".width-detect") : null;
//     if (target != null && window.innerWidth >= 992) {
//         target.forEach(function(find) {
//             imageresize(find);
//         });
//     }
// });
</script>

<style scoped>
/* @media (min-width: 992px) {
  .width-detect img {
    min-height: 230px;
  }
}
@media (min-width: 1200px) {
.width-detect img {
    min-height: 222px;
  }
}
@media (min-width: 1400px) {
.width-detect img {
    min-height: 259px;
  }
}
@media (min-width: 1600px) {
  .width-detect img {
    min-height: 296px;
  }
}
.width-detect img {
   min-height: 352px;
   object-fit: cover;
} */
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
</style>