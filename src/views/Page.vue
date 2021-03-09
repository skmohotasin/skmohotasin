<template>
  <section class="page" :documentId="documentId">
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
      <slices-block :slices="slices"/>
  </section>
</template>

<script>
// imports for all components
import HeaderPrismic from '../components/HeaderPrismic.vue'
import SlicesBlock from '../components/SlicesBlock.vue'



export default {
  name: 'page',
  components: {
    HeaderPrismic,
    SlicesBlock
  },
  data () {
    return {
      documentId: '',
       fields: {
        title: null,
        tagline: null,
        image: null,
        button_link: null,
        button_label: null
      },
      slices: []
    }
  },
  methods: {
    getContent (uid) {
      //Query to get post content
      this.$prismic.client.getByUID('page', uid)
        .then((document) => {
          
          if (document) {
            
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
    background:linear-gradient(to top left, #ff009c,#5b146f,#00a9ff,#ffd515);
    max-width: 5000px;
    margin: auto;
    max-height: 2000px;
    background-size:cover;
    background-blend-mode: hard-light;
    animation: hue-rotate alternate-reverse 10s infinite;
}


@keyframes hue-rotate {
  from {
    -webkit-filter: hue-rotate(0);
    -moz-filter: hue-rotate(0);
    -ms-filter: hue-rotate(0);
    filter: hue-rotate(0);
    opacity: 0.7;
  }
  to {
    -webkit-filter: hue-rotate(360deg);
    -moz-filter: hue-rotate(360deg);
    -ms-filter: hue-rotate(360deg);
    filter: hue-rotate(360deg);
    opacity: 0.9;
  }
}
</style>