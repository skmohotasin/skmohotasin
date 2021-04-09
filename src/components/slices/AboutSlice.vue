<template>
    <div class="row py-2 py-sm-2 py-md-3 py-lg-5">
      <div class="col-xxl-8 col-xl-8 col-lg-10 col-md-12 mx-auto text-center">
        <div class="row d-flex align-items-center justify-content-center">
          <div class="col-xl-6 col-lg-6 col-md-6 col-sm-12 py-2 py-md-0 mx-auto text-center">
            <prismic-image :field="slice.primary.featured_image" class="img-responsive"/>
          </div>
          <div class="col-xl-6 col-lg-6 col-md-6 col-sm-12 py-2 py-md-0 mx-auto text-center">
              <prismic-rich-text class="h5 heading-custom-color" :field="slice.primary.text"/>
              <prismic-rich-text class="custom-color h1 fw-bold pb-md-2" :field="slice.primary.testing"/>
              <prismic-rich-text class="description fw-light" :field="slice.primary.headline"/>
               <template v-if="$prismic.richTextAsPlain(slice.primary.link_label) !== ''">
                <p class="pt-2 pt-md-3">
                  <prismic-link  class="btn btn-circle" :field="slice.primary.link">{{ $prismic.richTextAsPlain(slice.primary.link_label) }}</prismic-link>
                </p>
               </template>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'about-slice'
}
</script>

<style scoped>
.btn-circle {
  text-decoration: none;
  color: #5b146f;
  border:2px solid #5b146f;
  border-radius: 48px;
  padding: 10px 100px;
}
.btn-circle:hover {
  color: #fff;
  border:2px solid #fff;
  background: #5b146f;
}
.custom-color{
  color:#5b146f;
}
.heading-custom-color{
  color: #ff009c;
}
<<<<<<< HEAD
</style>
=======

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
>>>>>>> parent of 67e0d02 (mobile updates)
