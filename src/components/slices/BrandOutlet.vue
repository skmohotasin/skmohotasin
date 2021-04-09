<template>
 <div class="row py-4 py-sm-2 py-md-3 py-lg-5">
    <div class="col-xxl-8 col-xl-8 col-lg-10 col-md-12 mx-auto text-center">
      <prismic-image :field="slice.primary.image" class="img-fluid"/>
    </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'brand-outlet'
}
<<<<<<< HEAD
</script>
=======
</script>

<style scoped>
.BOimage {
  width: 100%;
  padding-top:20px;
  
  
}


/* Media Queries */
@media (max-width: 320px) {
  .BOimage {
    padding-block-start: 50px;
    
    align-content: center;
    width: 100%;

  }
}
</style>
>>>>>>> parent of 67e0d02 (mobile updates)
