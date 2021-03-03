<template>
  <section class='image-gallery content-section'>
    <prismic-rich-text :field="slice.primary.gallery_title"/>
    <div class="gallery">
      <div v-for="item in slice.items" :key="item.id" class="gallery-item">
        <prismic-image :field="item.image"/>
        <prismic-rich-text :field="item.image_description"/>
        <p>
          <prismic-link :field="item.link" class="gallery-link">{{ $prismic.richTextAsPlain(item.link_label) }}</prismic-link>
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'approach-slice'
}
</script>

<style scoped>
.gallery {
    background-color: #5b146f;
  display: -webkit-box;  /* OLD - iOS 6-, Safari 3.1-6, BB7 */
  display: -ms-flexbox;  /* TWEENER - IE 10 */
  display: -webkit-flex; /* NEW - Safari 6.1+. iOS 7.1+, BB10 */
  display: flex;
  -webkit-flex-wrap: wrap;
   flex-wrap: wrap;
  -webkit-justify-content: space-between; 
  justify-content: space-between; 
  
}
.gallery-item {
  -webkit-box-flex: 0 1 50%;
  -moz-box-flex:  0 1 50%;
  -webkit-flex:  0 1 50%;
  -ms-flex:  0 1 50%;
  flex: 0 1 50%;
  padding-top: 50px;
}


/*Media Queries*/
@media (min-width: 320px) {
  .gallery-item {
    
    -webkit-box-flex:auto;
    -moz-box-flex:  auto;
    -webkit-flex:  auto;
    -ms-flex:  auto;
    flex: auto; 
    
  }
  

}

@media (min-width: 768px) {
  .gallery-item {
    
  -webkit-box-flex: 0 1 30%;
  -moz-box-flex:  0 1 30%;
  -webkit-flex:  0 1 30%;
  -ms-flex:  0 1 30%;
  flex: 0 1 30%;
   
    
  }
}

</style>
