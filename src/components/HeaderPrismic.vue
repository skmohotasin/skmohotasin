<template>
  <header class="site-header">
    <router-link to="/" class="logo">
    
    
    </router-link>
    <nav>
      <ul style="padding-left:10px;padding-right:10px">
        <li v-for="menuLink in menuLinks" :key="menuLink.id">
          <prismic-link :field="menuLink.link">{{ $prismic.richTextAsPlain(menuLink.label) }}</prismic-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  
  name: 'HeaderPrismic',
  data () {
    return {
      menuContent: [],
      menuLinks: []
    }
  },
  methods: {
    getMenu () {
      //Query to get menu content
      this.$prismic.client.getSingle('menu')
        .then((menuContent) => {
          this.menuContent = menuContent
          this.menuLinks = menuContent.data.menu_links
        })
    },
  },
  created () {
    this.getMenu()
  }

  
}
</script>

<style>
/* Site header */
.site-header {
  height: 30px;
  padding: 0px 0;
  
}
.site-header,
.site-header a {
  
  color: #ffffff;
  font-weight: 700;
  
}
.site-header nav a:hover {
  color: #72767B;
}
.homepage .site-header,
.homepage .site-header a {
  color:white;

}
.homepage .site-header nav a:hover {
  color: #1052d6;
}
.site-header .logo {
  display: inline-block;
  font-size: 22px;
  font-weight: 900;
}
.site-header nav {
  float: right;
}
.site-header nav ul {
  margin: 0;
}
.site-header nav li {
  display:initial;
  margin-left: 40px;
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

@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px) {

 .site-header nav li {
    margin-block-end: 0px;
  }

.homepage .site-header,
.homepage .site-header a {
  font-size: 14px;
  padding: 10px;
  padding-top: 10px;
  width: 100%;
}
.homepage .site-header a {
 
  padding-inline-end: 0px;
  
}
.site-header nav li {
   display: inline;
   margin-left:0px;
   margin-right: 0px;
}

.homepage-banner{
 
  line-height: 0;
}



  }

</style>

