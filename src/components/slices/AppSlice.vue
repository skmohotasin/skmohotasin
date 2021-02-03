<template>
  <section class='app-slice content-section'>
    <prismic-rich-text :field="slice.primary.gallery_title"/>
    <div class="gallery">
      <div v-for="item in slice.items" :key="item.id" class="gallery-item">
        
        <div class="description1">
          <h3>
        <prismic-rich-text  class="title1" :field="item.image_description1"/>
        <prismic-rich-text class="desc1" :field="item.desc1"/>
          </h3>
        </div>

        <div class="description2">
          <h3>
        <prismic-rich-text  class="title2" :field="item.image_description2"/>
        <prismic-rich-text class="desc2" :field="item.desc2"/>
          </h3>
        </div>

      <div class="description3">
        <h2>
        <prismic-rich-text  class="title3" :field="item.image_description3"/>
        <prismic-rich-text class="desc3" :field="item.desc3"/>
        </h2>
      </div>
<p> <prismic-link class="approachbutton" :field="slice.primary.link">{{ $prismic.richTextAsPlain(slice.primary.link_label) }}</prismic-link> </p>
      </div>
    
        
    </div>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'app-slice'
}
</script>

<style scoped>
.gallery-item {
  display: flex;
  align-items: flex-end;
}
.gallery-item > div {
  /*8ackground-color: #f1f1f1;*/
  width: 500px;
  margin: 20px;
  text-align: center;
  font-size: 30px;
  padding: 10px;
  
}
.description1{
  background-color: palevioletred;
  padding-left:10px;
  padding-right:10px;
}
.description2{
  background-color: DodgerBlue;
  padding-left:10px;
  padding-right:10px;
  
}
.description3{
  background-color: purple;
  padding-left:10px;
  padding-right:10px;
}
.title1{
  font-weight: bolder;
  color: white;
  font-size: 30pt;
  padding-bottom: 0px;
}
.title2{
  font-weight: bolder;
  color: white;
  font-size: 30pt;
}
.title3{
  font-weight: bolder;
  color: white;
  font-size: 30pt;
}
.desc1{
  color:white;
  font-size: 16pt;
}
.desc2{
  color:white;
  font-size: 16pt;
}
.desc3{
  color:white;
  font-size: 16pt;
  font-weight: lighter;
}

/* Media Queries */
@media (max-width: 320px) {
  .gallery-item {
    padding: 50px;
    display: block;
    flex-direction: column;
  
  }
  .description1{
    
    max-width:150px;
  }
    .description2{
    max-width:150px;
  }
    .description3{
    max-width:150px;
  }
  .title1{
    font-size: 18px;
  }
  .title2{
    font-size: 20px;
  }
  .title3{
    font-size: 20px;
  }
  .desc1{
    
  font-size: 10px;
}
 .desc2{
    
  font-size: 10px;
}
 .desc3{
    
  font-size: 10px;
}
}
@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 667px) 
 {
   .gallery-item {
    padding: 90px;
    display: block;
    flex-direction: column;
  
  }
  .description1{
    
    max-width:150px;
  }
    .description2{
    max-width:150px;
  }
    .description3{
    max-width:150px;
  }
  .title1{
    font-size: 18px;
  }
  .title2{
    font-size: 20px;
  }
  .title3{
    font-size: 20px;
  }
  .desc1{
    
  font-size: 10px;
}
 .desc2{
    
  font-size: 10px;
}
 .desc3{
    
  font-size: 10px;
}
 }
</style>
