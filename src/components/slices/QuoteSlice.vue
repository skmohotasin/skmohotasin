<template>
<div class="row py-2 py-sm-2 py-md-3 py-lg-5">
  <div class="col-xl-8 col-lg-10 col-md-10 mx-auto text-center">
    <blockquote class="blockquote blockquote-custom-color">
      <prismic-rich-text :field="slice.primary.quote_text"/>
    </blockquote>
    <template v-if="$prismic.richTextAsPlain(slice.primary.author) !== ''">
     <footer class="Source-custom-color"><prismic-rich-text :field="slice.primary.author" :class="''"/></footer>
    </template>
  </div>
</div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'quote-slice'
}
</script>

<style scoped>
.Source-custom-color{
  color:#5b146f;
}
.blockquote-custom-color{
  color: #ff009c;
}
</style>
