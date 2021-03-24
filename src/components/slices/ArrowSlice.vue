<template>
  <div class="row">
    <div class="col-4 col-md-2 mx-auto">
      <div :class="'icon ' + slice.primary.arrow_direction">
        <div class="arrow"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'arrow-slice'
}
</script>
<style scoped>
.left.icon,.right.icon {
  position: relative;
  height: 60px;
}
.left .arrow, .right .arrow {
  position: absolute;
  top: 25px;
  width: 40%;
  height: 5px;
  background-color: #e10098;
  box-shadow: 0 3px 5px rgba(0, 0, 0, .2);
  animation: arrow 700ms linear infinite;
}

.left .arrow {
  left: 30%;
}
.right .arrow {
  right: 30%;
}

.left .arrow::after, .left .arrow::before, .right .arrow::after, .right .arrow::before {
  content: '';
  position: absolute;
  width: 30px;
  height: 5px;
  background-color: #e10098;
}

.left .arrow::after, .left .arrow::before {
  right: -6px;
}
.right .arrow::after, .right .arrow::before {
   left: -6px;
}

.left .arrow::after {
  top: -9px;
  transform: rotate(45deg);
}

.left .arrow::before {
  top: 9px;
  box-shadow: 0 3px 5px rgba(0, 0, 0, .2);
  transform: rotate(-45deg);
}

.right .arrow::after {
  top: -9px;
  transform: rotate(-45deg);
}

.right .arrow::before {
  top: 9px;
  box-shadow: 0 3px 5px rgba(0, 0, 0, .2);
  transform: rotate(45deg);
}

.up.icon,.down.icon {
  position: relative;
  height: 65px;
  margin-bottom: 3rem;
}
.up .arrow, .down .arrow  {
  position: absolute;
  top: 0;
  width: 5px;
  height: 60px;
  left: calc(50% - 2.5px);
  background-color: #e10098;
  -webkit-box-shadow: 0 3px 5px rgb(0 0 0 / 20%);
  box-shadow: 0 3px 5px rgb(0 0 0 / 20%);
  -webkit-animation: arrow 700ms linear infinite;
  animation: arrow 700ms linear infinite;
}

.up .arrow::after, .up .arrow::before, .down .arrow::after, .down .arrow::before {
  content: '';
  position: absolute;
  width: 30px;
  height: 5px;
  background-color: #e10098;
}

.up .arrow::after {
  top: 6px;
  left: -22px;
  transform: rotate(-45deg);
}

.up .arrow::before {
  top: 6px;
  left: -3px;
  box-shadow: 0 3px 5px rgba(0, 0, 0, .2);
  transform: rotate(45deg);
}
.down .arrow::after {
  bottom: 6px;
  left: -22px;
  transform: rotate(45deg);
}

.down .arrow::before {
  bottom: 6px;
  left: -3px;
  box-shadow: 0 3px 5px rgba(0, 0, 0, .2);
  transform: rotate(-45deg);
}
</style>