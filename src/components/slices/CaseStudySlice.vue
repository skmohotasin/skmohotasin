<template>
<div class="row py-2 py-sm-2 py-md-3 py-lg-5">
    <div class="col-xxl-8 col-xl-8 col-lg-10 col-md-12 mx-auto text-center">
        <prismic-rich-text class="heading-custom-color pb-md-2 mb-3 mb-md-4" :field="slice.primary.band_name"/>
        <prismic-rich-text class="title-custom-color mb-4 mb-md-5"  :field="slice.primary.title"/>
        <prismic-rich-text class="subtitle-custom-color mb-3 mb-md-4"  :field="slice.primary.subtitle"/>
        <prismic-rich-text class="description mb-3 mb-md-4" :field="slice.primary.description"/>
        <template v-if="$prismic.richTextAsPlain(slice.primary.link_label) !== ''">
            <p class="pt-2 pt-md-3">
                <prismic-link  class="'btn btn-circle" :field="slice.primary.link">{{ $prismic.richTextAsPlain(slice.primary.link_label) }}</prismic-link>
            </p>
        </template>
    </div>
    <div class="col-xxl-8 col-xl-10 col-lg-12 col-md-12 mx-auto pt-4 pt-lg-5 mx-auto px-0 text-center gallery-item text-center">
        <template v-for="(item,index) in slice.items">
            <div :key="item.id" :class="'col-xl-' + (12/slice.items.length) + ' col-lg-' + (12/slice.items.length) + ' col-md-6 col-xs-12 mb-4 mb-md-0 mx-auto px-0 text-center gallery-item item-'+ index">
                <div class="gallery-item-inner">
                    <prismic-image :field="item.image" class="img-responsive"/>
                </div>
            </div>
        </template>
    </div>
</div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'case-study-slice'
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
  border:2px solid#ff009c;
  background: #ff009c;
}
.heading-custom-color{
  color: #ff009c;
}
.title-custom-color{
  color:#5b146f;
}
.subtitle-custom-color{
  color:#333333;
}
.description {
  color: #464646;
}
</style>
