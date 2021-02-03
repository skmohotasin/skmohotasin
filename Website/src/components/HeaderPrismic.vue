<template>
  <header class="site-header">
    <router-link to="/" class="logo">finalmile</router-link>
    <nav>
      <ul>
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
  padding: 20px 0;
  
}
.site-header,
.site-header a {
  
  color: #484d52;
  font-weight: 700;
  
}
.site-header nav a:hover {
  color: #72767B;
}
.homepage .site-header,
.homepage .site-header a {
  color:black;

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
  display: inline-block;
  margin-left: 40px;
}

.homepage-banner {
 background:linear-gradient(to top left, #500778 ,#E10098 50%,#00A9E0,#FEDB00);
    width:100%;
    height:100vh;
    background-size:cover;
    /*background-blend-mode: hard-light;*/
    background-blend-mode: color-dodge;
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










/* Media Queries */
@media (max-width: 1060px) {
  .site-header {
    padding-left: 20px;
    padding-right: 20px;
  }
}
@media (max-width: 767px) {
  .site-header {
    height: auto;
  }
  .homepage .site-header {
    position: absolute;
    left: 0;
    right: 0;
  }
  .site-header .logo {
    display: block;
    text-align: center;
  }
  .site-header nav {
    float: none;
    text-align: center;
  }
  .site-header nav li {
    display: inline-block;
    margin-left: 10px;
    margin-right: 10px;
  }
}
</style>

