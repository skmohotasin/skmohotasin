<template>
  <section class="homepage" :documentId="documentId">
    <!-- Vue tag to add header component -->
    <header-prismic/>
    <!-- Button to edit document in dashboard -->
        <div class="container-fluid homepage-banner">
          <div class="row">
            <div class="col-xl-12 col-md-12 col-sm-12 col-xs-12 p-0 m-0 text-center">
                 <div class="col-xl-12 col-md-12 col-sm-12 col-xs-12 py-5 my-5 text-center">
                    <p class="h1 text-white pb-5 px-3 m-0">{{ $prismic.richTextAsPlain(fields.tagline) }}</p>   
                    <prismic-link class="btn-homepage-circle" :field="fields.button_link">{{ $prismic.richTextAsPlain(fields.button_label) }}</prismic-link>
                 </div>
                 <div class="wave">
                    <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none">
                      <path d="M985.66,92.83C906.67,72,823.78,31,743.84,14.19c-82.26-17.34-168.06-16.33-250.45.39-57.84,11.73-114,31.07-172,41.86A600.21,600.21,0,0,1,0,27.35V120H1200V95.8C1132.19,118.92,1055.71,111.31,985.66,92.83Z" class="shape-fill"></path>
                    </svg>
                  </div>
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
  name: 'home-page',
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
    getContent () {
      //Query to get home content
      this.$prismic.client.getSingle('homepage')
        .then((document) => {
          if (document) {
            this.documentId = document.id;
            const banner = document.data.homepage_banner[0];
            this.fields.image = banner.image.url;
            this.fields.title = banner.title;
            this.fields.tagline = banner.tagline;
            this.fields.button_link = banner.button_link;
            this.fields.button_label = banner.button_label;
            //Set slices as variable
            this.slices = document.data.page_content
          } else {
            //returns error page
            this.$router.push({ name: 'not-found' })
          }
        })
    },
  },
  created () {
    this.getContent()
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

.wave {
  max-height: 100px;
  display: flex;
}
.wave svg {
  fill: #FFFFFF;
}
</style>