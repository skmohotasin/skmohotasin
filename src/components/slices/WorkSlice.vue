<template>
  <section class='highlight content-section'>
  <div class="container">
    <div class="highlight-left">
      <prismic-rich-text style="margin-bottom:-2em" class="text" :field="slice.primary.text"/>
      <prismic-rich-text style="margin-bottom:-2em" class="testing" :field="slice.primary.testing"/>
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
  padding-bottom:70px;
}

/*Media Queries*/
@media (min-width: 320px) {
  

   .container {
        display:block;
        text-align: left;

  }

.highlight-left{
  width:100%;
  align-items: left;
  padding-bottom: 0px;
  padding-left:10px
  
}

.highlight-right{
 
  width:90%;
}

  .text{
    
    text-align: center;
  }
  .testing{
    
    text-align: center;
    font-size: 30pt;
  }

  .work_button{

    font-size: 15px;
  }
  .h3{
    font-size: 50px;
  }

}

@media (min-width: 768px) {

  .container {
        display:flex;
  }

}
  


</style>
