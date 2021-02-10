<template>
  <section class='full-width-image content-section'>
    <div class="BOimage">
      <prismic-image :field="slice.primary.image"/>
    </div>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'brand-outlet'
}
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