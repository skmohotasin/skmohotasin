<template>
  <footer class="footer">


<div class="container">
    <div class="highlight-left">
    <div class="description">
    <h1><strong> final</strong>mile </h1>
    <p class="desc"> Description </p>
    <p class="text"> For General Queries : <em>12345678</em></p>
    <p class="text" > Email : <em>@gmail.com</em> </p>
    </div>

    <div class="logos">
    <a href="https://facebook.com" target="_blank" rel="noopener">
      <img class="logo" src="../assets/img/facebook-logo.png" alt="Facebook" width="20" height="30">
    </a>
    <a href="https://Instagram.com" target="_blank" rel="noopener">
      <img class="logo" src="../assets/img/instagram-logo.png" alt="Facebook" width="20" height="30">
    </a>
    <a href="https://twitter.com" target="_blank" rel="noopener">
      <img class="logo" src="../assets/img/twitter-logo.png" alt="Twitter" width="20" height="30">
    </a>
    <a href="https://linkedin.com" target="_blank" rel="noopener">
      <img class="logo" src="../assets/img/linkedin-logo.png" alt="Linkedin" width="20" height="30">
    </a>

    </div>
    </div>

    <div class="highlight-center">
      <p> </p>
      <h4><strong> Quick Links</strong></h4>
      <br><br>
      <p>Home</p>
      <p>About Us </p>
      <p>Approach</p>
      <p>Results</p>
      <p>Our Brands</p>
      <p>Contact Us</p>

    </div>
    <div class="highlight-right">
      <h4><strong>Newsletter</strong></h4>
      <block-gallery
      <p> Sign up for getting latest updates </p>
      <p><textarea v-model="message" placeholder="Your email"></textarea></p>

      <a href="https://google.com" target="_blank" rel="noopener">
      <img class="logo" src="../assets/img/newsletter-logo.png" alt="Newsletter">
    </a>
    
    </div>
    
    
</div>

<div>
<p class="copyright"> @ 2020 Copyright.  All Rights Reserved by FinalMile </p>

</div>


  </footer>
</template>

<script>
export default {
  name: 'FooterPrismic'
}
</script>

<style scoped> 
.footer {
  max-width: 5000px;
  margin: auto;
  text-align: center;
  border-top: 1px solid #DADADA;
  color:white;
  
  
}
.logo {
  width: 20px;
  height: 20px;
  padding-left:10px;
  padding-right:10px;
}

.container {
   
        display: flex;
        align-items: center;
        justify-content: center;
        background: #500778;
        justify-content:space-around;
        vertical-align: baseline;
      max-width: 5000px;
  margin: auto;
       
      }

.highlight-right {
  flex-basis: 40%;
  padding-right:40px;
  padding-left:40px;
  order: 4;  
  text-align: center;
}

.highlight-center {
    padding-right:20px;
    padding-left:20px;
    text-align:left;
    
}

.highlight-left {
  padding-right:70px;
  padding-left:40px;
}

.text{
  color:rgb(219, 59, 86);
  font-size: 12pt;
}

.text em{
  color:white;
  font-size: 10pt;
}
.description{
  text-align: left;
}
.desc{
  color:white;
  font-weight: normal;
}

p{
  margin-bottom: 1em;
}
.copyright{
  color:white;
  background-color: #500778;
  font-size: 6pt;
}

@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px) {

    .container{
      display: block;
    }
    .description{
      text-align: center;
    }
    .highlight-left{
      padding-bottom: 15px;
    }
    .highlight-center{
      text-align: center;
      padding-bottom: 15px;
    }
    
  }

</style>
