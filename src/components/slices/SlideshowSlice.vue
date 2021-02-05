<template>
  <section class='highlight content-section'>
  <div class="container">
    <div class="highlight">
      <prismic-rich-text class="text" :field="slice.primary.text"/>
    </div>


<div class="window">
      <span id="slide-1"></span>
      <span id="slide-2"></span>
      <span id="slide-3"></span>
      <span id="slide-4"></span>
      <span id="slide-5"></span>
      <div class="image-container">
        <img src="https://archive.org/download/altometa_gmail_E/a.jpg" class="slide">
        <img src="https://archive.org/download/altometa_gmail_E/b.jpg" class="slide">
        <img src="https://archive.org/download/altometa_gmail_E/c.jpg" class="slide">
        <img src="https://archive.org/download/altometa_gmail_E/d.jpeg" class="slide">
        <img src="https://archive.org/download/altometa_gmail_E/e.jpg" class="slide">
      </div>
      <div class="button-container">
        <a href="#slide-1" class="slider-button"></a>
        <a href="#slide-2" class="slider-button"></a>
        <a href="#slide-3" class="slider-button"></a>
        <a href="#slide-4" class="slider-button"></a>
        <a href="#slide-5" class="slider-button"></a>
      </div>
    </div>

    </div>
    
  </section>
</template>

<style scoped>
body {
  background-color: #000;
}

.window {
  width: 450px;
  height: 300px;
  margin-left: auto;
  margin-right: auto;
  overflow: hidden;
  text-align: center;
}

.image-container {
  width: 2250px;
  height: 300px;
  position: relative;
  transition: left 2s;
  -webkit-transition: left 2s;
  -moz-transition: left 2s;
  -o-transition: left 2s;
}

.slide {
  float: left;
  margin: 0;
  padding: 0;
}

.button-container {
  top: -20px;
  position: relative;
}

.slider-button {
  display: inline-block;
  
  height: 10px;
  width: 10px;
  border-radius: 5px;
  background-color: #fff;
}

#slide-1:target ~ .image-container {
  left: 0;
}

#slide-2:target ~ .image-container {
  left: -450px;
}

#slide-3:target ~ .image-container {
  left: -900px;
}

#slide-4:target ~ .image-container {
  left: -1350px;
}

#slide-5:target ~ .image-container {
  left: -1800px;
}
</style>

<script>
export default {
  props: ['slice'],
  name: 'slideshow-slice'
}


</script>