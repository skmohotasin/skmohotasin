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
  color:#ff009c;
  font-size:12pt;
  text-align: center;
}
.testing{
 color:#5b146f;
 font-weight: bolder;
 font-size: 36pt;
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
  display: grid;
  text-align: center;
  margin-left:50px;
  margin-right:50px;
 
}
.button:hover {
  background: #c8c9cb;
}

 

</style>
