<template>
 <div class="row py-3 py-md-3 py-lg-5 my-4 my-md-0 custom-bg-color">
    <div class="col-xl-8 col-lg-10 col-md-10 mx-auto text-center">
      <div class="row">
          <div class="col-xl-4 col-lg-4 col-md-4 text-center">
             <counter1></counter1>
            <prismic-rich-text class="text-white pt-2" :field="slice.primary.text1"/>
          </div>
          <div class="col-xl-4 col-lg-4 col-md-4 text-center">
            <counter3></counter3>
            <prismic-rich-text class="text-white pt-2" :field="slice.primary.text5"/>
          </div>
          <div class="col-xl-4 col-lg-4 col-md-4 text-center">
            <counter5></counter5>
            <prismic-rich-text class="text-white pt-2" :field="slice.primary.text11"/>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'number-slice'
}
</script>

<style scoped>
.custom-bg-color {
  background:#5b146f;
}
counter1, counter3, counter5 {
  font: 700 50px system-ui;
}
@media (min-width: 1200px) { 
  counter1, counter3, counter5 {
    font: 700 70px system-ui;
  }
 }
@property --num {
  syntax: "<integer>";
  initial-value: 0;
  inherits: false;
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
  padding: 0rem;
  color:#ffffff;
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
    --num: 130000;
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
  padding: 0rem;
  color:#ffffff;
}

@keyframes counterthree {
  from {
    --num: 0;
  }
  to {
    --num: 374000;
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
  padding: 0rem;
  color:#ffffff;
}

@keyframes counterfive {
  from {
    --num: 0;
  }
  to {
    --num: 500000;
  }
}

counter5::after {
  content: counter(num);
}
</style>




