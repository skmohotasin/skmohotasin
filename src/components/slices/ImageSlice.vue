<template>
<div class="row py-2 py-sm-2 py-md-3 py-lg-5">
    <div class="col-xxl-8 col-xl-12 col-lg-12 col-md-12 mx-auto text-center">
      <div class="row">
        <div class="position-relative col-lg-4 col-lg-4 col-md-4 col-sm-6 col-xs-12 p-0">
          <img src="http://placehold.it/423x423" class="img-responsive">
          <div class="position-absolute top-50 start-50 translate-middle">
              <p style="padding-top:100px;font-size:35px" class="name text-white">Kelsey</p>
              <p  class="role text-white">Digital Marketing & Creative Lead</p>
          </div>
        </div>
        <div class="position-relative col-lg-4 col-lg-4 col-md-4 col-sm-6 col-xs-12 p-0">
          <img src="http://placehold.it/423x423" class="img-responsive">
          <div class="position-absolute top-50 start-50 translate-middle">
              <p style="padding-top:100px;font-size:35px" class="name text-white">Shule</p>
              <p class="role text-white">Technology & Operations Lead</p>
          </div>
        </div>
        <div class="position-relative col-lg-4 col-lg-4 col-md-4 col-sm-6 col-xs-12 p-0">
          <img src="http://placehold.it/423x423" class="img-responsive">
          <div class="position-absolute top-50 start-50 translate-middle">
              <p style="padding-top:100px;font-size:35px" class="name text-white">Shelley</p>
              <p class="role text-white">Brand & Innovation Lead</p>
          </div>
        </div>
       <div class="position-relative col-lg-4 col-lg-4 col-md-4 col-sm-6 col-xs-12 p-0">
          <img src="http://placehold.it/423x423" class="img-responsive">
          <div class="position-absolute top-50 start-50 translate-middle">
              <p style="padding-top:100px;font-size:35px" class="name text-white">Chris</p>
              <p class="role text-white">CFO</p>
          </div>
        </div>
        <div class="position-relative col-lg-4 col-lg-4 col-md-4 col-sm-6 col-xs-12 p-0">
          <img src="http://placehold.it/423x423" class="img-responsive">
          <div class="position-absolute top-50 start-50 translate-middle">
              <p style="padding-top:100px;font-size:35px" class="name text-white"></p>
              <p class="role text-white">Final Mile Crew</p>
          </div>
        </div>
        <div class="position-relative col-lg-4 col-lg-4 col-md-4 col-sm-6 col-xs-12 p-0">
          <img src="http://placehold.it/423x423" class="img-responsive">
          <div class="position-absolute top-50 start-50 translate-middle">
              <p style="padding-top:100px;font-size:35px" class="name text-white">Carol</p>
              <p class="role text-white">Merchandising Lead</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ['slice'],
  name: 'image-slice'
}
</script>

<style scoped>
.position-absolute{
  border: 1px solid #ccc;
  background:linear-gradient(to top left, #ff009c,#00a9ff);
  width:100%;
  height: 100%;
}


</style>
