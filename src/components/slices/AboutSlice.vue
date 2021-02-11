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
  width: 100%;
  
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
/*iphones*/
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px)
  {

  .container {
        padding-top: 0px;
        display:inline-flex;
        text-align: center;
        flex-wrap: wrap;
        margin-block-start:0px;   
        padding: 0px;   
  }
  .highlight-right {
    text-align:left;
    margin-bottom: 0px;
    margin-inline-end: 0px;
  }
.highlight-left{
  width: 300px;
  align-items: left;
  padding-bottom: 0px;
  padding-left: 0px;
  padding-right: 0px;
}
  .text{
    
    text-align: left;
    font-size: 14pt;
  }
  .testing{
    text-align: left;
    font-size: 25pt;
  }
  .work_button{
    font-size: 10px;
  }
  .h3{
    color:Red;
  }
}
@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 667px)
   
 {
  .container {
        padding-top: 0px;
        display:inline-flex;
        text-align: center;
        flex-wrap: wrap;
        margin-block-start:0px;   
        padding: 0px;   
  }
  .highlight-right {
    text-align:left;
    margin-bottom: 0px;
    margin-inline-end: 0px;
  }
.highlight-left{
  width: 300px;
  align-items: left;
  padding-bottom: 0px;
  padding-left: 0px;
  padding-right: 0px;
}
  .text{
    
    text-align: left;
    font-size: 14pt;
  }
  .testing{
    text-align: left;
    font-size: 25pt;
  }
  .work_button{
    font-size: 10px;
  }
  .h3{
    color:Red;
  }
}
@media only screen 
  and (min-device-width: 768px) 
  and (max-device-width: 1024px){
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
  width: 100%;
  
}
.text{
  font-weight: bolder;
  color:red;
  font-size:16pt;
}
.testing{
 color:purple;
 font-weight: bolder;
 font-size: 36pt;
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
  }

</style>
