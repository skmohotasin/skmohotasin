<template>
  <section class="homepage">
    <!-- Vue tag to add header component -->
    
    <!-- Button to edit document in dashboard -->
    <prismic-edit-button :documentId="documentId"/>
    <section class="homepage-banner" style="height: 50vh; width:100%">
    <!-- Template for page title. -->
    <header-prismic/>
      <div class="custom-shape-divider-bottom-1611087996" style="position:relative">
        <h2 class="banner-title">
          {{ $prismic.richTextAsPlain(fields.title) }}
        </h2>
        <!-- Template for page tagline -->
        <p class="banner-description">{{ $prismic.richTextAsPlain(fields.tagline) }}</p>
        
        <prismic-link class="banner-button" :field="fields.button_link">
          {{ $prismic.richTextAsPlain(fields.button_label) }}
        </prismic-link>
        <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none">
        <path d="M985.66,92.83C906.67,72,823.78,31,743.84,14.19c-82.26-17.34-168.06-16.33-250.45.39-57.84,11.73-114,31.07-172,41.86A600.21,600.21,0,0,1,0,27.35V120H1200V95.8C1132.19,118.92,1055.71,111.31,985.66,92.83Z" class="shape-fill"></path>
        </svg>
      </div>
      
    </section>
    
    <div class="container">
      <!-- Slices block component -->
      <slices-block :slices="slices"/>
    </div>
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
    SlicesBlock,
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

<style>
.custom-shape-divider-bottom-1611087996 {
    position: relative;
    bottom: 0;
    left: 0;
    width: 100%;
    overflow: hidden;
    line-height: 0;
}
.custom-shape-divider-bottom-1611087996 svg {
    position: relative;
    display: block;
    width: calc(152% + 1.3px);
    height: 50vh;
}
.custom-shape-divider-bottom-1611087996 .shape-fill {
    fill: #FFFFFF;
}
.homepage-banner {
  margin: -70px 0 80px;
  padding: 5em 0 8em;
  background-position: center center;
  background-size: cover;
  color: #ffffff;
  line-height: 1.75;
  text-align: left;
  
}
.banner-content {
  text-align: left;
}
.banner-title,
.banner-description {
  width: 90%;
  max-width: 490px;
  text-align: left;
  
}
.banner-title {
  color: #ffffff;
  font-size: 60px;
  font-weight: 700;
  line-height: 80px;
  text-align: left;
  padding-left: 90px;
  ;
}
.banner-button {
  background: purple;
  border-radius: 50px;
  color: white;
  font-size: 18px;
  font-weight: 700;
  padding: 15px 40px;
  margin: 90px;
  
  
}
.banner-button:hover {
  background: #c8c9cb;
  
}


/** For mobile devices **/
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px) {
    
    
    .custom-shape-divider-bottom-1611087996 svg {
        width: calc(179% + 1.3px);
    }
    .banner-button{
      font-size: 10px;
    }
    .banner-title{
      font-size: 14px;
      text-align: left;
      padding-left: 10px;
    }
   .homepage-banner{
      
      width:100%
    }
}
</style>