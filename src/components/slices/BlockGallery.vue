<template>
  <section class='figure-slice content-section'>
    <prismic-rich-text :field="slice.primary.gallery_title"/>
    <div class="gallery">
      <div v-for="item in slice.items" :key="item.id" class="gallery-item">
        <prismic-rich-text :field="item.image_description"/>
      </div>
    </div>
    
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'block-gallery'
}
</script>

<style scoped>
.gallery {
  display: -webkit-box;  /* OLD - iOS 6-, Safari 3.1-6, BB7 */
  display: -ms-flexbox;  /* TWEENER - IE 10 */
  display: -webkit-flex; /* NEW - Safari 6.1+. iOS 7.1+, BB10 */
  display: flex;
  -webkit-flex-wrap: nowrap;
   flex-wrap: nowrap;
   background:darkblue;
    -webkit-justify-content: space between; 
  justify-content: space-between;
 
}
.gallery-item {
  padding-top:70px;
  padding-left:40px;
  padding-right:40px;
  text-align:center;
  font-size:20px;
  -webkit-box-flex: 0 1 18%;
  -moz-box-flex:  0 1 18%;
  -webkit-flex:  0 1 18%;
  -ms-flex:  0 1 18%;
  flex: 0 1 18%; 
}




</style>
