<template>
 <div class="row py-2 py-sm-2 py-md-3 py-lg-5 mt-3 mt-md-0">
    <template  v-if="$prismic.richTextAsPlain(slice.primary.app_title) !== ''">
      <div class="col-xxl-8 col-xl-8 col-lg-12 col-md-12 mx-auto text-center">
        <prismic-rich-text :field="slice.primary.app_title" :class="'pb-3 pb-lg-5'"/>
      </div>
    </template>
    <div class="col-xxl-8 col-xl-12 col-lg-12 col-md-12 mx-auto text-center">
      <div class="row">
         <div v-for="(item,index) in slice.items" :key="item.id" class="col-xl-4 col-lg-4 col-md-4 d-flex align-bottom">
              <div :class="'col-xxl-11 col-lg-12 col-md-12 mb-4 mb-md-0 m-md-auto px-5 px-md-1 px-lg-3 px-xxl-5 padding-t-b-3 py-md-'+ ( 5 + index) + ' text-center bg-color-0'+ (1 + index)">
                <prismic-rich-text  class="text-white" :field="item.block_title"/> 
                  <p class="desciption text-white">{{ $prismic.richTextAsPlain(item.block_description) }}
                    <template  v-if="$prismic.richTextAsPlain(item.link_label) !== ''">
                      <prismic-link :field="item.link" :class="'text-decoration-none btn-color-'+ index">{{ $prismic.richTextAsPlain(item.link_label) }}</prismic-link>
                    </template>
                  </p>
              </div>
         </div>
      </div>
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
.btn-color-0 {
  color: #00a9ff;
}
.btn-color-1,.btn-color-2 {
  color: #ff009c;
}
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
<<<<<<< HEAD
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
=======
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
@media (max-width: 320px) 
  and (max-device-width: 480px) {
  .gallery-item {
    padding: 10px;
    
    display: fit-content;
    flex-direction: column;
  
  }
  .description1{
    
    max-width:200px;
    max-height: 100px;
  }
    .description2{
    max-width:200px;
      max-height: 150px;
  }
    .description3{
    max-width:200px;
    max-height: 200px;
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
  line-height: 2;
 
}



}
@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 667px) 
 {
   .gallery-item {
    padding: 60px;
    display: block;
    flex-direction: column;
  
  }
  .description1{
    
    max-width:200px;
    max-height: 100px;
  }
    .description2{
      max-width:200px;
      max-height: 150px;
  }
    .description3{
    max-width:200px;
    max-height: 200px;
    line-height: 80%;
  }
  .title1{
    font-size: 18px;
  }
  .title2{
    font-size: 20px;
  }
  .title3{
    font-size: 20px;
>>>>>>> parent of 67e0d02 (mobile updates)
  }
  .desc1{
    
  font-size: 10px;
}
<<<<<<< HEAD

=======
 .desc2{
    
  font-size: 10px;
}
 .desc3{
    
  font-size: 10px;
}
 }
>>>>>>> parent of 67e0d02 (mobile updates)
</style>
