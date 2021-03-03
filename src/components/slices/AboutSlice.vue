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
 font-size: 30pt;
}

.aboutbutton {
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
.aboutbutton:hover {
  background: #c8c9cb;
}



/*Media Queries*/
@media (min-width: 320px) {
  .container{
    display:block;
    width:100%;
   
    
  }
 
    
  
  

}
/*Small devices (landscape phones, less than 768px)*/
@media (min-width: 768px) {
.container{
    display:block;
    width:90%;
    
  }
}

/*Medium devices (tablets, less than 992px)*/
@media (min-width: 992px) {
.container{
    display:flex;
    width:90%;
    justify-content: center;
  }
}

/*Large devices (desktops, less than 1200px)*/
@media (min-width: 1200px) {
.container{
    display:flex;
    width:100%;
    padding-left:0px;
    
  }
}






</style>
