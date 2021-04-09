<template>
   <div class="row py-2 py-sm-2 py-md-3 py-lg-5">
    <div class="col-xxl-8 col-xl-8 col-lg-10 col-md-12 mx-auto text-center">
      <prismic-rich-text class="h5 heading-custom-color" :field="slice.primary.text"/>
      <prismic-rich-text class="custom-color h1 fw-bold" :field="slice.primary.testing"/>
      <prismic-rich-text class="description fw-light" :field="slice.primary.headline"/>
      <p class="pt-2">
        <prismic-link  class="btn btn-circle" :field="slice.primary.link">{{ $prismic.richTextAsPlain(slice.primary.link_label) }}</prismic-link>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'desc-slice'
}
</script>

<style scoped>
.btn-circle {
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
.custom-color{
  color:#5b146f;
}
<<<<<<< HEAD
.heading-custom-color{
  color: #ff009c;
}
=======
/* Media Queries */
@media (max-width: 320px) {
 
.text{
 
  text-align: center;
  padding-bottom: 0px;
  
}

.testing{
  padding-top: 0px;
  font-size: 25pt;
  text-align: center;
  
}
.button{
  
  align-content: right;
}
}

@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 667px)
   
 {
   .text{
 
  text-align: center;
  padding-bottom: 0px;
  
}

.testing{
  padding-top: 0px;
  font-size: 25pt;
  text-align: center;
  
}
.button{
  
  align-content: right;
}
 }

 

>>>>>>> parent of 67e0d02 (mobile updates)
</style>
