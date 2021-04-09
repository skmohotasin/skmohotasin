<template>
<<<<<<< HEAD
 <div class="row py-4 py-md-3 py-lg-5 mt-4 mt-sm-5 mb-4 mb-md-3 custom-bg-color">
    <template  v-if="$prismic.richTextAsPlain(slice.primary.number_slice_title) !== ''">
      <div class="col-xxl-8 col-xl-8 col-lg-10 col-md-12 mx-auto text-center">
        <prismic-rich-text :field="slice.primary.number_slice_title" :class="'pb-3 pb-lg-5 text-white'"/>
      </div>
    </template>
    <div class="col-xxl-8 col-xl-8 col-lg-10 col-md-12 mx-auto text-center">
      <div class="row">
          <div v-for="item in slice.items" :key="item.id" class="col-xl-4 col-lg-4 col-md-4 text-center">
             <div class="number">
               <number
                :from="0"
                :to="item.number"
                :format="theFormat"
                :duration="15"
                :delay="1"
                 easing="Power0.easeNone"/>
             </div>
             <P class="text-white pt-2">{{ item.title }}</p>
          </div>
      </div>
    </div>
=======
  <section class='highlight content-section'>
  <div class="container">
  <div class="container1">
    <counter1>
      <prismic-rich-text class="text" :field="slice.primary.text"/>
    </counter1>
     <prismic-rich-text class="comment1" :field="slice.primary.text"/>
   </div>
   <div class="container3">
    <counter5>
      <prismic-rich-text class="text4" :field="slice.primary.text4"/>
    </counter5>
   </div>
    <div class="container2">
    <counter3>
      <prismic-rich-text class="text10" :field="slice.primary.text10"/>
    </counter3>
   </div>
>>>>>>> parent of 67e0d02 (mobile updates)
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'num-slice',
   methods: {
        theFormat(number) {
            return number.toLocaleString("en", {minimumFractionDigits: 0,maximumFractionDigits: 0,});
        }
    }
}
</script>

<style scoped>
.custom-bg-color {
  background:#5b146f;
}
.number span {
  font: 700 50px system-ui;
  padding: 0rem;
  color:#ffffff;
}
@media (min-width: 1200px) { 
  .number span {
    font: 700 70px system-ui;
  }
<<<<<<< HEAD
 }
=======
}


counter5::after {
  content: counter(num);
}



.container{
  display: -webkit-box;  /* OLD - iOS 6-, Safari 3.1-6, BB7 */
  display: -ms-flexbox;  /* TWEENER - IE 10 */
  display: -webkit-flex; /* NEW - Safari 6.1+. iOS 7.1+, BB10 */
  display: flex;
  -webkit-flex-wrap: nowrap;
   flex-wrap: nowrap;
   background:#5b146f;
  justify-content: space-around;
  margin-block-start: 0px;
  
  
}
.containerr{
   display: -webkit-box;  /* OLD - iOS 6-, Safari 3.1-6, BB7 */
  display: -ms-flexbox;  /* TWEENER - IE 10 */
  display: -webkit-flex; /* NEW - Safari 6.1+. iOS 7.1+, BB10 */
  display: flex;
  -webkit-flex-wrap: nowrap;
  flex-wrap: nowrap;
  background:#5b146f;
  justify-content: space-around;
  padding:0px;
  
  
  
}
/* Media Queries */

  @media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px) {


counter5::after {
  
  font-size: 15px;  
}
counter3::after {
  font-size: 15px;
  padding: 0rem;
}
counter1::after {
  font-size: 15px;
  padding: 0rem;
}
.containerr{
  font-size: 6px;
}
.container1{
  height: 10px;
}
.text1{
  font-size:6pt;
}

.container{
  
  background-color: #5b146f;
  padding-left:0px;
  padding-right:0px;
  justify-content: space-around;
  width: 200px;
}

.containerr{
  visibility: hidden;
}



}

>>>>>>> parent of 67e0d02 (mobile updates)
</style>




