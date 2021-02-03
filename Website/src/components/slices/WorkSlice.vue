<template>
  <section class='highlight content-section'>
  <div class="container">
    <div class="highlight-left">
      <prismic-rich-text class="text" :field="slice.primary.text"/>
      <prismic-rich-text class="testing" :field="slice.primary.testing"/>
      <prismic-rich-text :field="slice.primary.title"/>
      <prismic-rich-text :field="slice.primary.headline"/>
      <p>
        <prismic-link class="work_button" :field="slice.primary.link">{{ $prismic.richTextAsPlain(slice.primary.link_label) }}</prismic-link>
      </p>
    </div>
    <div class="highlight-right">
      <prismic-image :field="slice.primary.featured_image"/>
    </div>
  </div>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'work-slice'
}
</script>

<style scoped>

.container {
        display: flex;
        align-items: center;
        justify-content: center;
        padding-top:0px;
        text-align:justify;
      }
.highlight {
  position: relative;
  overflow: auto;
}
.highlight-left {
  width: 43%;
  float: left;
}
.highlight-right {
  padding-left:40px;
  width: 48%;
  float: right;
}
.text{
  font-weight: bolder;
  color:red;
  font-size:10pt;
}
.testing{
 color:purple;
 font-weight: bolder;
 font-size: 50pt;
}
.work_button {
  background:white;
  border-radius: 50px;
  border:2px solid purple;
  color: purple;
  font-size: 14px;
  font-weight: 700;
  padding: 15px 40px;
}
.work_button:hover {
  background: #c8c9cb;
}



/* Media Queries */
@media (max-width: 320px) {
  .highlight-left,
  .highlight-right {
    width: 100%;
    float: none;
  }
}
</style>
