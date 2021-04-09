<template>
  <section class='highlight content-section'>
  <div class="container">
    <div class="highlight">
      <prismic-rich-text class="text" :field="slice.primary.text"/>
      <prismic-rich-text class="testing" :field="slice.primary.testing"/>
      <prismic-rich-text class="testing1" :field="slice.primary.testing1"/>
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
  name: 'case-slice'
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

.testing1{
 color:black;
 font-weight: bolder;
 font-size: 23pt;
 text-align: center;
 
}


.button {
  background:white;
  border-radius: 70px;
  border:2px solid #ff009c;
  color: #ff009c;
  font-size: 14px;
  font-weight: 700;
  padding: 20px 40px;
  position:relative;
  top: 50%;
  left: 40%;
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
 
}
.button:hover {
  background: #c8c9cb;
}
@media (min-width: 320px) {
  .container{
    display:block;
    padding:30px;

  }

  
}


 

</style>
