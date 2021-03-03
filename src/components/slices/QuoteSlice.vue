<template>
  <section class='content-section quote'>
    <blockquote class="block-quotation">{{ $prismic.richTextAsPlain(slice.primary.quote_text) }}</blockquote>
    <p style="text-align:center;font-family:'Poppins', sans-serif;color:#5b146f;padding-top:20px">Sarah Kennedy - CEO Calocurb</p>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'quote-slice'
}
</script>

<style scoped>
.quote blockquote {
  display: block;
  /*font-family: 'Lora', Serif;*/
  font-family:'Poppins', sans-serif; 
  font-size: 25px;
  
  
  color: #ff009c; 
  letter-spacing : 1.14;
  line-height: 1.5em;
  quotes: "\201C""\201D""\2018""\2019";
  text-align: center;
}
.quote blockquote:before,
.quote blockquote:after {
  color: #ff009c;
  content: open-quote;
  /*font-family: 'Lora', Serif;*/
 font-family:'Poppins', sans-serif;
  font-size: 2em;
  font-weight: 500;
  line-height: 0.1em;
  margin-left: 10px;
  margin-right: 10px;
  vertical-align: -0.3em;
}
.quote blockquote:after {
  content: close-quote;
}

</style>
