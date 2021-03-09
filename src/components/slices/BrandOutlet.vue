<template>
 <div class="row py-4 py-sm-2 py-md-3 py-lg-5">
    <div class="col-xl-8 col-lg-10 col-md-10 mx-auto text-center">
      <prismic-image :field="slice.primary.image" class="img-fluid"/>
    </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'brand-outlet'
}
</script>