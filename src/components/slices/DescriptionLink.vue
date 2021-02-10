<template>
  <section class='highlight content-section'>
  <div class="container">
    <div class="highlight">
      <prismic-rich-text class="text" :field="slice.primary.text"/>
      <prismic-rich-text class="testing" :field="slice.primary.testing"/>
      <prismic-rich-text class="description" :field="slice.primary.headline"/>
    </div>
    
    </div>
  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'description-link'
}
</script>

<style scoped>
.highlight {
  position: relative;
  
}

.container {
        display: flex;
        align-items: center;
        justify-content: center;
        padding-top:0px;
        
      }

.text{
  font-weight: bolder;
  color:#ff009c;
  font-size:12pt;
  text-align: center;
}
.testing{
 color:#5b146f;
 font-weight: bolder;
 font-size: 36pt;
 text-align: center;
 
}

.button {
  background:white;
  border-radius: 50px;
  border:2px solid purple;
  color: purple;
  font-size: 12px;
  font-weight: 700;
  padding: 15px 40px;
  margin: 0;
  position: absolute;
  top: 120%;
  left: 50%;
  margin-right: -50%;
  transform: translate(-50%, -50%)
}
.button:hover {
  background: #c8c9cb;
}


/* Media Queries */
@media (max-width: 320px) {
  .highlight-left,
  .highlight-right {
    width: 100%;
    float: none;
  }
}
</style>
