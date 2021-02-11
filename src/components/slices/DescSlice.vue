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
  name: 'desc-slice'
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
  padding: 25px 40px;
  margin-left:400px;
 
 
}
.button:hover {
  background: #c8c9cb;
}
/* Media Queries */
@media (max-width: 320px) {
 
.text{
 
  text-align: center;
  padding-bottom: 0px;
  
}

.testing{
  padding-top: 0px;
  font-size: 25pt;
  text-align: center;
  
}
.button{
  
  align-content: right;
}
}

@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 667px)
   
 {
   .text{
 
  text-align: center;
  padding-bottom: 0px;
  
}

.testing{
  padding-top: 0px;
  font-size: 25pt;
  text-align: center;
  
}
.button{
  
  align-content: right;
}
 }

 

</style>
