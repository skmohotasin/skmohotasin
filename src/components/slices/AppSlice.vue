<template>
 <div class="row py-2 py-sm-2 py-md-3 py-lg-5">
    <div class="col-xxl-8 col-xl-12 col-lg-12 col-md-12 mx-auto text-center">
     <prismic-rich-text :field="slice.primary.gallery_title"/>
    </div>
    <div class="col-xxl-8 col-xl-12 col-lg-12 col-md-12 mx-auto text-center">
      <div class="row" v-for="item in slice.items" :key="item.id">
         <div class="col-xl-4 col-lg-4 col-md-4 d-flex align-bottom">
            <div class="col-xxl-11 col-lg-12 col-md-12 mb-4 mb-md-0 m-md-auto px-5 px-md-1 px-lg-3 px-xxl-5 padding-t-b-3 py-md-5 text-center bg-color-01">
            <prismic-rich-text  class="h3 text-white" :field="item.image_description1"/>
            <prismic-rich-text class="desciption text-white" :field="item.desc1"/>
            </div>
         </div>
         <div class="col-xl-4 col-lg-4 col-md-4 d-flex align-bottom">
            <div class="col-xxl-11 col-lg-12 col-md-12 mb-4 mb-md-0 m-md-auto px-5 px-md-1 px-lg-3 px-xxl-5 padding-t-b-3 py-md-6 text-center bg-color-02">
            <prismic-rich-text  class="h3 text-white" :field="item.image_description2"/>
            <prismic-rich-text class="desciption text-white" :field="item.desc2"/>
            </div>
         </div>
         <div class="col-xl-4 col-lg-4 col-md-4 d-flex align-bottom">
            <div class="col-xxl-11 col-lg-12 col-md-12 m-md-auto px-5 px-md-1 px-lg-3 px-xxl-5 padding-t-b-3 py-md-7 text-center bg-color-03">
            <prismic-rich-text  class="h3 text-white" :field="item.image_description3"/>
            <prismic-rich-text class="desciption text-white"  :field="item.desc3"/>
            </div>
         </div>
      </div>
    </div>
    <div class="col-xxl-8 col-xl-12 col-lg-12 col-md-12 mx-auto text-center">
      <template v-if="$prismic.richTextAsPlain(slice.primary.link_label) !== ''">
        <p class="pt-2 pt-md-3">
          <prismic-link  class="btn btn-circle" :field="slice.primary.link">{{ $prismic.richTextAsPlain(slice.primary.link_label) }}</prismic-link>
        </p>
      </template>
    </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'app-slice'
}
</script>

<style scoped>
.bg-color-01, .bg-color-02, .bg-color-03 {
  border-radius: 10px;
}
.bg-color-01 {
  background-color: #ff009c;
}
.bg-color-02 {
  background-color: #00a9ff;
}
.bg-color-03 {
  background-color: #5b146f;
}
.padding-t-b-3 {
  padding-top: 2rem;
  padding-bottom: 2rem;
}
@media (min-width: 768px) {
  .py-md-6 {
    padding-top: 4rem;
    padding-bottom: 4rem;
  }
  .py-md-7 {
    padding-top: 6rem;
    padding-bottom: 6rem;
  }
}
.btn-circle {
 text-decoration: none;
  color: #ff009c;
  border:2px solid #ff009c;
  border-radius: 48px;
  padding: 10px 20px;
}
.btn-circle:hover {
  color: #fff;
  border:2px solid #fff;
  background: #ff009c;
}

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
  padding: 25px;
  
}
.description1{
  background-color: #ff009c;
  border-radius: 10px;
  padding-left:10px;
  padding-right:10px;
  
  
}
.description2{
  background-color: #00a9ff;
  border-radius: 10px;
  padding-left:10px;
  padding-right:10px;
  
}
.description3{
  background-color: #5b146f;
  border-radius: 10px;
  padding-left:10px;
  padding-right:10px;
  line-height: 2em;
}
.title1{
  font-weight: bolder;
  color: white;
  font-size: 30pt;
  padding-bottom: 0px;
  line-height: 1em;
}
.title2{
  font-weight: bolder;
  color: white;
  font-size: 30pt;
  line-height: 1em;
}
.title3{
  font-weight: bolder;
  color: white;
  font-size: 30pt;
  line-height: 1em;
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
@media (min-width: 320px) {
  
  .gallery-item {
    display:block;
    
  
  }
  .description1{
    
    max-width:75%;
    max-height: 150px;
    
  }
    .description2{
    max-width:75%;
    max-height: 200px;
  }
    .description3{
    max-width:75%;
    max-height: 225px;
  }
  .title1{
    font-size: 20px;
    padding:0px;
  }
  .title2{
    font-size: 20px;
  }
  .title3{
    font-size: 20px;
    
  }
  .desc1{
  padding-top:0px;
  font-size: 20px;
  
}
 .desc2{
    
  font-size: 20px;
}
 .desc3{
    
  font-size: 20px;
  line-height: 2;
 
}
}

@media (min-width: 768px) {

    .gallery-item {
    display:flex;

  }
  .description1{
    
    max-width:85%;
    max-height: 230px;
    
  }
    .description2{
    max-width:85%;
    max-height: 330px;
  }
    .description3{
    max-width:85%;
    max-height: 400px;
  }
}



</style>
