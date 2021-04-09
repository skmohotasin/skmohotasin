<template>
  <section class='figure-slice content-section'>
    <prismic-rich-text :field="slice.primary.gallery_title"/>
    <div class="gallery">
      <div v-for="item in slice.items" :key="item.id" class="gallery-item">
        <prismic-rich-text :field="item.image_description"/>
      </div>
    </div>
    <div class="gallery">
      <div v-for="item in slice.items" :key="item.id" class="gallery-item2">
        
        <prismic-rich-text :field="item.image_description2"/>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'figure-slice'
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
  height: 100%;
  width: 1000px;
  margin: 0;
  padding-left: 0;
  
 
}
.gallery-item {
  padding-top:70px;
  padding-left:40px;
  padding-right:40px;
  text-align:center;
  font-size:50px;
  -webkit-box-flex: 0 1 18%;
  -moz-box-flex:  0 1 18%;
  -webkit-flex:  0 1 18%;
  -ms-flex:  0 1 18%;
  flex: 0 1 18%; 
}
.gallery-item2 {
  padding-top:0px;
  padding-bottom:50px;
  padding-left:40px;
  padding-right:40px;
  text-align:center;
  font-size:15px;
  -webkit-box-flex: 0 1 18%;
  -moz-box-flex:  0 1 18%;
  -webkit-flex:  0 1 18%;
  -ms-flex:  0 1 18%;
  flex: 0 1 18%; 
}



</style>
