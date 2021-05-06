<template>
  <section class="page" :documentId="documentId" v-bind:style="{ backgroundImage: 'url(' + backgroundImage.url + ')'}">
    <!-- Vue tag to add header component -->
    <header-prismic/>
    <!-- Button to edit document in dashboard -->
        <div class="container-fluid homepage-banner mb-4 mb-lg-0">
          <div class="row">
              <div class="col-xl-12 col-md-12 col-sm-12 col-xs-12 py-4 m-2 py-lg-5 m-lg-0 text-center">
              </div>
            </div>
         </div>
      <!-- Slices block component -->
      <slices-block :slices="slices" />
    <footer-prismic />
  </section>
</template>

<script>
// imports for all components
import HeaderPrismic from '../components/HeaderPrismic.vue'
import SlicesBlock from '../components/SlicesBlock.vue'
import FooterPrismic from '../components/FooterPrismic.vue'

export default {
  name: 'page',
  components: {
    HeaderPrismic,
    SlicesBlock,
    FooterPrismic
  },
  data () {
    return {
      documentId: '',
      backgroundImage: [],
      slices: []
    }
  },
  methods: {
    getContent (uid) {
      //Query to get post content
      this.$prismic.client.getByUID('page', uid)
        .then((document) => {
          
          if (document) {
            this.documentId = document.id
            this.backgroundImage = document.data.background_image
            //Set slices as variable
            this.slices = document.data.page_content
          } 
          else {
            //returns error page
            this.$router.push({ name: 'not-found' })
          }
        })
    }
  },
  created () {
    this.getContent(this.$route.params.uid)
  },
  beforeRouteUpdate (to, from, next) {
    this.getContent(to.params.uid)
    next()
  }
}
</script>

<style scoped>
@media (min-width: 768px) {
  .page {
    background-size: 100vw 95vh;
  }
}
@media (max-width: 767px) {
  .page {
    background-size: 100vw 100vh;
  }
}
.btn-homepage-circle {
  text-decoration: none;
  color: #fff;
  border:2px solid #ff009c;
  background:#ff009c;
  border-radius: 48px;
  padding: 10px 40px;
}
.btn-homepage-circle:hover {
  color: #fff;
  border:2px solid #ff009c;
  background: transparent;
}


.homepage-banner {
    background: linear-gradient(115deg, #2a5ba8, #b70f76);
    background-size: 175% 100%;

    -webkit-animation: AnimationName 6s ease infinite;
    -moz-animation: AnimationName 6s ease infinite;
    animation: AnimationName 6s ease infinite;
}

@-webkit-keyframes AnimationName {
    0%{background-position:0% 15%}
    50%{background-position:100% 86%}
    100%{background-position:0% 15%}
}
@-moz-keyframes AnimationName {
    0%{background-position:0% 15%}
    50%{background-position:100% 86%}
    100%{background-position:0% 15%}
}
@keyframes AnimationName {
    0%{background-position:0% 15%}
    50%{background-position:100% 86%}
    100%{background-position:0% 15%}
}
</style>