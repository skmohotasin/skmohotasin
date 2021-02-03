<template>
  <section class='highlight content-section'>
  <div class="container">
    <div class="highlight">
      <prismic-rich-text class="text" :field="slice.primary.text"/>
      <prismic-rich-text class="testing" :field="slice.primary.testing"/>
      <prismic-rich-text class="description" :field="slice.primary.headline"/>
      <p>
        <prismic-link  class="button" :field="slice.primary.link">{{ $prismic.richTextAsPlain(slice.primary.link_label) }}</prismic-link>
      </p>
    </div>
    
    </div>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'description-slice'
}
</script>

<style scoped>
.highlight {
  position: relative;
  
}

.container {
        display: flex;
        align-items: center;
        justify-content: center;
        padding-top:0px;
        
      }

.text{
  font-weight: bolder;
  color:red;
  font-size:10pt;
  text-align: center;
}
.testing{
 color:purple;
 font-weight: bolder;
 font-size: 50pt;
 text-align: center;
 
}

.button {
  background:white;
  border-radius: 50px;
  border:2px solid purple;
  color: purple;
  font-size: 14px;
  font-weight: 700;
  padding: 15px 40px;
  margin: 0;
  position: absolute;
  top: 120%;
  left: 50%;
  margin-right: -50%;
  transform: translate(-50%, -50%)
}
.button:hover {
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
