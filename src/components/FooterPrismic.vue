<template>
  <footer class="footer">


<div class="container">
    <div class="highlight-left">
    <div class="description">
    <h1><strong> final</strong>mile </h1>
    <p class="desc"> We come from the bottom of the world where inventiveness and grit come together naturally to create potential. <br>Our job is to catapult kiwi ventures to unlock their business possibilities. As owners we love what we do and it’s time to share that know-how with you.  </p>
    </div>

    <!--

    <div class="logos" style="text-align:left">
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

    -->
    </div>

    

    <div class="highlight-center">
           
      <p style="margin:0em"><a href="https://finalmile.co.nz/" style="color:white;font-size:16pt">Home</a></p>
      <p style="margin:0em"><a href="https://finalmile.co.nz/page/about-us" style="color:white;font-size:16pt">About Us</a> </p>
      <p style="margin:0em"><a href="https://finalmile.co.nz/page/about-us" style="color:white;font-size:16pt">Approach</a></p>
      <p style="margin:0em"><a href="https://finalmile.co.nz/page/about-us" style="color:white;font-size:16pt">Results</a></p>
      <p style="margin:0em"><a href="https://finalmile.co.nz/page/our-brands" style="color:white;font-size:16pt">Our Brands</a></p>
      <p style="margin:0em"><a href="https://finalmile.co.nz/page/page-1" style="color:white;font-size:16pt">Careers</a></p>
      <p style="margin:0em"><a href="https://finalmile.co.nz/page/page-1" style="color:white;font-size:16pt">Partner with us</a></p>

    </div>

    <!--
    <div class="highlight-right">
      <h4><strong>Newsletter</strong></h4>
      
      <p> Sign up for getting latest updates </p>
      <p ><textarea style="border-radius:10px;width:180px" v-model="message" placeholder="Your email"></textarea>

      <a href="https://google.com" target="_blank" rel="noopener">
      <img  class="logoo" src="../assets/img/newsletter-logo.png" alt="Newsletter" width="35" height="35" style="padding-left:10px">

      
    </a>
    </p>
    
    </div>
    -->

    <div class="highlight-right">
      
    <p class="text"> Phone : <em>06 8766773</em></p>
    <p class="text" > Email : <em>webstore@thebrandoutlet.co.nz</em> </p>
    
    </div>

    
</div>

<!--
<div>
<p class="copyright"> @ 2020 Copyright.  All Rights Reserved by FinalMile </p>

</div>

-->


  </footer>
</template>

<script>
export default {
  name: 'FooterPrismic'
}
</script>

<style scoped> 

::placeholder {
  padding:5px;
}
.footer {
  max-width: 5000px;
  margin: auto;
  text-align: center;
  border-top: 1px solid #DADADA;
  color:#ffffff;
  
  
}
.logo {
  width: 20px;
  height: 20px;
  padding-left:10px;
  padding-right:10px;
  
}

.container {
   
        display:flex;
        justify-content: center;
        background:#5b146f;
        max-width: 5000px;
        padding-top:50px;
       
       
      }


.highlight-center {
    padding-right:0px;
    padding-left:0px;
    text-align:left;
     width:700px;
}

.highlight-left {
  padding-right:300px;
  padding-left:50px;
}
.highlight-right{
  width:700px;
  padding-right: 0px;
  padding-left: 0px;
  text-align:left;
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
  background-color: #5b146f;
  font-size: 6pt;
}

@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px) {
.desc{
  color:white;
  font-weight: normal;
  font-size:16pt;
  padding-left: 15px;
  
  text-align: left;
}
.container{
  display: grid;
}
.description{
  text-align: left;
  padding-left: 35pt;
}
.highlight-left{
  padding-bottom: 15px;
  padding-right:0px;
  padding-left:0px;
}
.highlight-center{
  text-align: left;
  padding-left:35pt;
  padding-bottom: 15px;
  padding-right:0px;
  width:300px;
  
}
}




</style>
