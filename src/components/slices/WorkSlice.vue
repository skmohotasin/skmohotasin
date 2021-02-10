<template>
  <section class='highlight content-section'>
  <div class="container">
    <div class="highlight-left">
      <prismic-rich-text class="text" :field="slice.primary.text"/>
      <prismic-rich-text class="testing" :field="slice.primary.testing"/>
      <prismic-rich-text class="title" :field="slice.primary.title"/>
      <prismic-rich-text class="headline" :field="slice.primary.headline"/>
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
  color:#ff009c;
  font-size:12pt;
}
.testing{
 color:#5b146f;
 font-weight: bolder;
 font-size: 36pt;
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

.title{
  padding-top:0px;
}



/* Media Queries */
@media (max-width: 320px) {

  .container {
        display:reverse;
        text-align: left;
        flex-wrap: wrap;
        
        
  }
  .highlight-right {
    float: none;
    text-align:left;
    margin-bottom: 0px;
    margin-inline-end: 0px;
    
  }
.highlight-left{
  width: 200px;
  align-items: left;
  padding-bottom: 0px;
  padding-left: 70px;
  padding-right: 50px;
}

  .text{
    
    text-align: center;
  }
  .testing{
    
    text-align: center;
    font-size: 15pt;
  }

  .work_button{

    font-size: 10px;
  }
}

@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 667px)
   
 {

   .container {
        display:reverse;
        text-align: left;
        flex-wrap: wrap;
        
        
  }
  .highlight-right {
    float: none;
    text-align:left;
    margin-bottom: 0px;
    margin-inline-end: 0px;
    
  }
.highlight-left{
  width: 200px;
  align-items: left;
  padding-bottom: 0px;
  padding-left: 70px;
  padding-right: 50px;
}

  .text{
    
    text-align: center;
  }
  .testing{
    
    text-align: center;
    font-size: 20pt;
  }

  .work_button{

    font-size: 15px;
  }
  .h3{
    font-size: 50px;
  }

 }

 @media only screen 
  and (min-device-width: 768px) 
  and (max-device-width: 1024px){

     .testing{
    
    text-align: left;
    font-size: 50px;
  }

  }
</style>
