<template>
  <section class='highlight content-section'>
  <div class="container">
  <div class="container1">
    <counter1>
      <prismic-rich-text class="text" :field="slice.primary.text"/>
    </counter1>
     <prismic-rich-text class="comment1" :field="slice.primary.text"/>
   </div>
   <div class="container3">
    <counter5>
      <prismic-rich-text class="text4" :field="slice.primary.text4"/>
    </counter5>
   </div>
    <div class="container2">
    <counter3>
      <prismic-rich-text class="text10" :field="slice.primary.text10"/>
    </counter3>
   </div>
  </div>


  <div class="containerr">
  
<counter2>
      <prismic-rich-text class="text1" :field="slice.primary.text1"/>
    </counter2>

    <counter6>
      <prismic-rich-text class="text5" :field="slice.primary.text5"/>
    </counter6>

    <counter4>
      <prismic-rich-text class="text11" :field="slice.primary.text11"/>
    </counter4>

  </div>



  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'number-slice'
}
</script>

<style scoped>
@property --num {
  syntax: "<integer>";
  initial-value: 0;
  inherits: false;
}
.comment1{
  color:white;
}
counter1 {

-webkit-animation: counterone 10s ;
-moz-animation: counterone 10s ;
-ms-animation: counterone 10s ;
animation: counterone 10s ;

  /*animation: counterone 10s ;*/
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  counter-reset: num var(--num);
  font: 700 70px system-ui;
  padding: 0rem;
  color:gray;
}

@-webkit-keyframes counterone {
  from {
    --num: 0;
  }
  to {
    -webkit--num: 1000;
  }
}

@-moz-keyframes counterone {
  from {
    --num: 0;
  }
  to {
    --num: 1000;
  }
}

@keyframes counterone {
  from {
    --num: 0;
  }
  to {
    --num: 1000;
  }
}

counter1::after {
  content: counter(num);
}

counter3 {
  animation: counterthree 10s ;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  counter-reset: num var(--num);
  font: 700 70px system-ui;
  padding: 0rem;
  color:gray;
  
}

@keyframes counterthree {
  from {
    --num: 0;
  }
  to {
    --num: 3000;
  }
}

counter3::after {
  content: counter(num);
}

counter5 {
  animation: counterfive 10s ;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  counter-reset: num var(--num);
  font: 700 70px system-ui;
  padding: 0rem;
  color:gray;
}

@keyframes counterfive {
  from {
    --num: 0;
  }
  to {
    --num: 4000;
  }
}


counter5::after {
  content: counter(num);
}



.container{
  display: -webkit-box;  /* OLD - iOS 6-, Safari 3.1-6, BB7 */
  display: -ms-flexbox;  /* TWEENER - IE 10 */
  display: -webkit-flex; /* NEW - Safari 6.1+. iOS 7.1+, BB10 */
  display: flex;
  -webkit-flex-wrap: nowrap;
   flex-wrap: nowrap;
   background:darkblue;
  justify-content: space-around;
  margin-block-start: 0px;
}
.containerr{
   display: -webkit-box;  /* OLD - iOS 6-, Safari 3.1-6, BB7 */
  display: -ms-flexbox;  /* TWEENER - IE 10 */
  display: -webkit-flex; /* NEW - Safari 6.1+. iOS 7.1+, BB10 */
  display: flex;
  -webkit-flex-wrap: nowrap;
   flex-wrap: nowrap;
   background:darkblue;
  justify-content: space-around;
  height: 100%;
  width: 100%;
 
  
  
}
/* Media Queries */

  @media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px) {

.container{
  background-color: darkblue;
  padding:0em;
  
}

counter5::after {
  font-size: 35px;  
}
counter3::after {
  font-size: 35px;
  padding: 0rem;
}
counter1::after {
  font-size: 35px;
  padding: 0rem;
}
.containerr{
  font-size: 10px;
}
.container1{
  height: 20px;
}
 


}

</style>




