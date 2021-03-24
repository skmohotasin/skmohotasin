<template>
    <div :class="'d-grid ' + slice.primary.class_name">
    </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'blank-space'
}
</script>