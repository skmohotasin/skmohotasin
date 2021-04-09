<template>
   <div class="row">
    <template v-if="$prismic.richTextAsPlain(slice.primary.title) !== ''">
      <div class="col-xxl-12 col-xl-12 col-lg-12 col-md-12 mx-auto text-center fm-bg-purple py-3 py-md-4">
          <prismic-rich-text class="text-white mb-3 mb-md-4" :field="slice.primary.eyebrow_headline"/>
        <template v-if="$prismic.richTextAsPlain(slice.primary.title) !== ''">
          <prismic-rich-text :class="'text-white mb-3 mb-md-4'"  :field="slice.primary.title"/>
        </template>
        <template v-if="$prismic.richTextAsPlain(slice.primary.description) !== ''">
          <prismic-rich-text class="text-white mb-3 mb-md-4" :field="slice.primary.description"/>
        </template>
      </div>
    </template>
    <div class="col-xxl-12 col-xl-12 col-lg-12 col-md-12 mx-auto p-0">
      <div id="ImageSlider" class="carousel slide" data-bs-ride="carousel" data-bs-touch="true" data-bs-interval="false">
        <div class="custom-carousel-indicators d-none d-md-block">
            <template v-for="(item,index) in slice.items">
              <template v-if="index == 0">
                <button :key="item.id" type="button" data-bs-target="#ImageSlider" :data-bs-slide-to="index" class="active" aria-current="true" :aria-label="'Slide ' + (index + 1)">{{ item.year }}</button>
              </template>
              <template v-else>
                <button :key="item.id" type="button" data-bs-target="#ImageSlider" :data-bs-slide-to="index" :aria-label="'Slide ' + (index + 1)">{{ item.year }}</button>
              </template>
          </template>
        </div>
        <div class="carousel-inner">
          <template v-for="(item,index) in slice.items">
            <div v-if="index == 0" :key="item.id" :class="'carousel-item active'">
              <prismic-image :field="item.image" class="d-block w-100"/>
              <div class="carousel-caption">
                <prismic-rich-text :field="item.description"/>
              </div>
            </div>
            <div v-else :key="item.id" :class="'carousel-item'">
              <prismic-image :field="item.image" class="d-block w-100"/>
              <div class="carousel-caption">
                <prismic-rich-text :field="item.description"/>
              </div>
            </div>
          </template>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'images-slider'
}
</script>


<style scoped>
.custom-carousel-indicators {
  position: absolute;
  right: 0;
  bottom: 0;
  left: 5%;
  z-index: 2;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  padding: 0;
  margin-bottom: 1.5rem;
  list-style: none;
  margin-left: 0;
  margin-right: 0;
}
.custom-carousel-indicators [data-bs-target] {
  padding: 0;
  text-indent: 0;
  border: none;
  color: #fff;
  margin-right: 20px;
  background-color: transparent;
  -webkit-transition: all 0.25s ease;
  transition: all 0.25s ease;
}
.custom-carousel-indicators [data-bs-target].active, .custom-carousel-indicators [data-bs-target]:hover {
  color: #e10098;
  padding: 0 3px;
  font-weight: bold;
  background-color: transparent;        
}
@media (min-width: 768px) {
  .carousel-caption {
    position: absolute;
    right: 5%;
    bottom: 2.75rem;
    left: 5%;
    padding-top: 1.25rem;
    padding-bottom: 1.25rem;
    color: #fff;
    text-align: left;
  }
}
@media (max-width: 767px) {
  .carousel-caption {
    position: absolute;
    right: 0%;
    bottom: 0px;
    left: 15px;
    padding-top: 0;
    padding-bottom: 0;
    color: #fff;
    text-align: left;
  }
}
</style>

