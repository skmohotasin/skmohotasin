<template>
  <section class='imagesslider'>
<div> 
  <prismic-rich-text class="eyebrow_headline" :field="slice.primary.eyebrow_headline"/>
  <prismic-rich-text class="title" :field="slice.primary.title"/>
</div>

<div>
  <prismic-image :field="slice.primary.image"/>
  <prismic-rich-text class="description" :field="slice.primary.description"/>
</div>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'images-slider'
}
</script>


