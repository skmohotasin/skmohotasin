<template>
  <section class='highlight content-section'>
  <div class="container">
    <div class="highlight-right">
      <prismic-rich-text class="text" :field="slice.primary.text"/>
      <prismic-rich-text class="testing" :field="slice.primary.testing"/>
      <prismic-rich-text class="description" :field="slice.primary.headline"/>
      <p>
        <prismic-link class="aboutbutton" :field="slice.primary.link">{{ $prismic.richTextAsPlain(slice.primary.link_label) }}</prismic-link>
      </p>

    </div>
    <div class="highlight-left">
      <prismic-image :field="slice.primary.featured_image"/>
    </div>
    </div>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'about-slice'
}
</script>

<style scoped>
.highlight {
  position: relative;
  overflow: auto;
}

.container {
        display: flex;
        align-items: center;
        justify-content: center;
        padding-top:0px;
      }

.highlight-right {
  flex-basis: 70%;
  order: 2;
  padding-left: 40px;
  
}
.highlight-left {
  color: #CD5C5C;
  
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

.aboutbutton {
  background:white;
  border-radius: 50px;
  border:2px solid purple;
  color: purple;
  font-size: 14px;
  font-weight: 700;
  padding: 15px 40px;
}
.aboutbutton:hover {
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
