<template>
  <section class='image-gallery content-section'>
    <div class="responsive">
  <div class="galleryy">
    <div class="desc">Name</div>
    <div class="desc1">Role</div>
  </div>
</div>

<div class="responsive">
  <div class="galleryy">
    <div class="desc">Name</div>
    <div class="desc1">Role</div>
  </div>
</div>

<div class="responsive">
  <div class="galleryy">
    <div class="desc">Kelsey</div>
    <div class="desc1">Digital Partner</div>
  </div>
</div>
<div class="responsive">
  <div class="galleryy">
    <div class="desc">Name</div>
    <div class="desc1">Role</div>
  </div>
</div>
<div class="responsive">
  <div class="galleryy">
    <div class="desc">Name</div>
    <div class="desc1">Role</div>
  </div>
</div>
<div class="responsive">
  <div class="galleryy">
    <div class="desc">Name</div>
    <div class="desc1">Role</div>
  </div>
</div>
<div class="space"></div>
  </section>
</template>
<script>
export default {
  props: ['slice'],
  name: 'image-slice'
}
</script>
<style scoped>
div.galleryy {
  border: 1px solid #ccc;
  background:linear-gradient(to top left, #ff009c,#00a9ff);
  width:330px;
  height:300px;
 
}
div.galleryy:hover {
  border: 1px solid #777;
}
div.galleryy img {
    
  width: 100%;
  height: auto;
}
div.desc {
    color:white;
    font: bold;
    font-size: 20px;
    font-weight: 900;
    padding-top: 125px;
    text-align: center;
}
div.desc1 {
    color:white;
    font: bold;
    font-size: 25px;
    font-weight: 900;
    
    text-align: center;
}
* {
  box-sizing: border-box;
}
.responsive {
  padding: 0 0px;
  float: left;
  width: 33.3%;
 
}
div.space{
    padding:300px;
}



/*Media Queries*/
@media only screen and (max-width: 700px) {
  .responsive {
    width: 49.99999%;
    margin: 6px 0;
  }
}

@media only screen and (max-width: 500px) {
  .responsive {
    width: 100%;
  }
}

</style>
