<template>
  <span v-html="slice.primary.embed_field"></span>
  
</template>

<script type="text/javascript">
export default {
  props: ['slice'],
  name: 'form-slice', 
}
</script>

<style scoped>

.embed_field{
  width:100px;
  height: 100px;
}

</style>

