<template>
  <header class="site-header">
    <nav class="navbar navbar-expand-lg navbar-dark bg-trasparent mobile-modified">
      <div class="container-fluid">
        <router-link to="/" class="logo ms-2 ms-md-3 ms-xl-5 text-white"><strong> final</strong>mile</router-link>
        <button onclick="ColoredBackgroundFunction()" class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#mobilenav" aria-controls="mobilenav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="mobilenav" onclick="AjaxFunction()">
          <ul class="navbar-nav pt-5 px-3 px-sm-4 px-lg-0 pt-lg-0 ms-auto me-xl-5">
            <li v-for="menuLink in menuLinks" :key="menuLink.id" class="nav-item">
              <prismic-link :field="menuLink.link" index class="nav-link text-uppercase fadeInDown">{{ $prismic.richTextAsPlain(menuLink.label) }}</prismic-link>
            </li>
          </ul>
        </div>
      </div>
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
.site-header {
  position: relative;
}
.navbar-dark .navbar-nav .nav-link.router-link-exact-active {
  background: rgba(255, 255, 255, 0.73);
  color: #fff;
  border-radius: 30px;
    
  
}

.logo {
  text-decoration: none;
}
.navbar.mobile-modified {
  position: absolute;
  width: 100%;
  top: 15px;
  left: 0;
  z-index:1;
}
@media (min-width: 1400px) {
  .logo {
    font-size: 50px;
  }
}
@media (min-width: 1200px) {
  .logo {
    font-size: 40px;
  }
}
@media (min-width: 992px) {
  .navbar.mobile-modified {
    top: 15px;
  }
   .logo {
    font-size: 35px;
  }
}
@media (max-width: 991px) {
  #mobilenav{
    z-index:3;
    height: 100vh;
  }
  .navbar.mobile-modified {
    top: 0px;
  }
  .navbar.mobile-modified.colored-background {
    background-color: #5b146f;
    position:fixed;
  }
  .logo {
    font-size: 30px;
  }
}

@-webkit-keyframes fadeInDown {
    from {
        opacity:0;
        -webkit-transform: translatey(-10px);
        -moz-transform: translatey(-10px);
        -o-transform: translatey(-10px);
        transform: translatey(-10px);
    }
    to {
        opacity:1;
        -webkit-transform: translatey(0);
        -moz-transform: translatey(0);
        -o-transform: translatey(0);
        transform: translatey(0);
    }
}
@-moz-keyframes fadeInDown {
    from {
        opacity:0;
        -webkit-transform: translatey(-10px);
        -moz-transform: translatey(-10px);
        -o-transform: translatey(-10px);
        transform: translatey(-10px);
    }
    to {
        opacity:1;
        -webkit-transform: translatey(0);
        -moz-transform: translatey(0);
        -o-transform: translatey(0);
        transform: translatey(0);
    }
}
@keyframes fadeInDown {
    from {
        opacity:0;
        -webkit-transform: translatey(-10px);
        -moz-transform: translatey(-10px);
        -o-transform: translatey(-10px);
        transform: translatey(-10px);
    }
    to {
        opacity:1;
        -webkit-transform: translatey(0);
        -moz-transform: translatey(0);
        -o-transform: translatey(0);
        transform: translatey(0);
    }
}
.fadeInDown {
    -webkit-animation-name: fadeInDown;
    -moz-animation-name: fadeInDown;
    -o-animation-name: fadeInDown;
    animation-name: fadeInDown;
    -webkit-animation-fill-mode: both;
    -moz-animation-fill-mode: both;
    -o-animation-fill-mode: both;
    animation-fill-mode: both;
    -webkit-animation-duration: 1s;
    -moz-animation-duration: 1s;
    -o-animation-duration: 1s;
    animation-duration: 1s;
}
</style>