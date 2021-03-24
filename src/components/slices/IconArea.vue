<template>
  <div class="row">
      <div class="col-xxl-12 col-xl-12 col-lg-12 col-md-12 mx-auto py-5 fm-bg-purple text-center">
          <div class="row">
               <template v-if="$prismic.richTextAsPlain(slice.primary.title) !== ''">
                    <div class="col-xxl-8 col-xl-12 col-lg-12 col-md-12 mx-auto text-center">
                        <prismic-rich-text class="title-custom-color mb-3 mb-md-4" :field="slice.primary.title"/>
                    </div>
                </template>
                <div class="col-xxl-8 col-xl-12 col-lg-12 col-md-12 mx-auto text-center">
                    <div class="row">
                            <template v-for="(item) in slice.items">
                                <div :key="item.id" :class="'col-xl-' + (12/slice.items.length) + ' col-lg-' + (12/slice.items.length) + ' col-md-4 col-xs-12 mb-4 mb-md-0 mx-auto p-2 text-center'">
                                    <div class="px-5 py-4 mx-lg-5">
                                        <prismic-image :field="item.image" class="img-responsive"/>
                                    </div>
                                    <div class="text">
                                        <prismic-rich-text :field="item.details"/>
                                    </div>
                                </div>
                        </template>
                    </div>
                </div>
                <template v-if="$prismic.richTextAsPlain(slice.primary.description) !== ''">
                    <div class="col-xxl-8 col-xl-12 col-lg-12 col-md-12 mx-auto text-center">
                        <prismic-rich-text class="description mb-3 mb-md-4 mt-lg-4" :field="slice.primary.description"/>
                        <template v-if="$prismic.richTextAsPlain(slice.primary.label) !== ''">
                            <p class="pt-2 pt-md-3">
                                <prismic-link  class="'btn btn-circle" :field="slice.primary.link">{{ $prismic.richTextAsPlain(slice.primary.label) }}</prismic-link>
                            </p>
                        </template>
                    </div>
                </template>
          </div>
      </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'icon-area'
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
.title-custom-color,.description,.text{
  color:#ffffff;
}
@media (min-width: 1200px) {
    .btn-circle {
        padding: 15px 30px;
    }
}
</style>
