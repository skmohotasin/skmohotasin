<template>
  <section class="page">
   <!-- Vue tag to add header component -->
    
    <!-- Button to edit document in dashboard -->
    <prismic-edit-button :documentId="documentId"/>
    <section class="homepage-banner" style="height: 25vh; width:100%">
    <!-- Template for page title. -->
    <header-prismic/>
     <!-- <div class="custom-shape-divider-bottom-1611087996" style="position:relative"> -->
       <div>
          <div class="title"> 
            <strong> final</strong>mile 
           <img class="logo" src="../assets/img/logo_footprint.png" alt="Facebook" width="30" height="50">
           </div>
        

        
        <!-- Template for page tagline -->
        
       <h1 class="banner-description">
          {{ $prismic.richTextAsPlain(fields.tagline) }}

       </h1>
        
        <prismic-link class="banner-button" :field="fields.button_link">
          {{ $prismic.richTextAsPlain(fields.button_label) }}
        </prismic-link>
       <!-- <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none">
        <path d="M985.66,92.83C906.67,72,823.78,31,743.84,14.19c-82.26-17.34-168.06-16.33-250.45.39-57.84,11.73-114,31.07-172,41.86A600.21,600.21,0,0,1,0,27.35V120H1200V95.8C1132.19,118.92,1055.71,111.31,985.66,92.83Z" class="shape-fill"></path>
        </svg> -->
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
import HomePage from '../views/HomePage.vue'



export default {
  name: 'page',
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



/** 
.xyz {
    position: relative;
    bottom: 0;
    left: 0;
    width: 100%;
    
    overflow: hidden;
    line-height: 0;
}
.xyz svg {
    position: relative;
    display: block;
    width: calc(152% + 1.3px);
    height: 60vh;
}
.xyz .shape-fill {
    fill: #FFFFFF;
} */
.homepage-banner {
  margin: -70px 0 80px;
 
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
  color:white;
  
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


</style>