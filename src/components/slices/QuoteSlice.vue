<template>
<div class="row py-2 py-sm-2 py-md-3 py-lg-5">
  <div class="col-xl-8 col-lg-10 col-md-10 mx-auto text-center">
    <blockquote class="blockquote blockquote-custom-color">
      <p class="mb-0 pb-2">{{ $prismic.richTextAsPlain(slice.primary.quote_text) }}</p>
    </blockquote>
     <footer class="blockquote-footer Source-custom-color fw-bold"><cite title="Source Title">Sarah Kennedy - CEO Calocurb</cite></footer>
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
.blockquote p{
  display: block;
  quotes: "\201C""\201D""\2018""\2019";
}
.blockquote p:before,
.blockquote p:after {
  font-weight: 500;
  font-size: 2em;
  vertical-align: -0.3em;
  line-height: 0.1em;
}
.blockquote p:before {
  content: open-quote;
  margin-right: 0.2em;
}
.blockquote p:after {
  content: close-quote;
  margin-left: 0.2em;
}
</style>
