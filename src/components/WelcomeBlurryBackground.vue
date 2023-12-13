<script setup>

</script>

<template>

  <div class="animated">
    <div class="wrapper">
      <div class="one"></div>
      <div class="two"></div>
      <div class="three"></div>
      <div class="four"></div>
    </div>
  </div>

</template>

<style scoped>
.animated {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  z-index: 0;
}
.wrapper {
  width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;
}
.wrapper div {
  position: absolute;
  filter: blur(250px);
  opacity: 0.8;
  -webkit-filter: blur(250px);
}
.animated .one {
  border-radius: 100%;
  width: 1200px;
  height: 1200px;
  background-color: #67578a;
  left: -50px;
  top: -100px;
  z-index: 3;
  animation: fly 12s linear infinite;
  transform: rotate(0) translate(80px) rotate(0);
}
.animated .two {
  width: 1500px;
  height: 1800px;
  background-color: #99558d;
  bottom: -30px;
  left: -80px;
}
.animated .three {
  border-radius: 100%;
  width: 100%;
  height: 100%;
  bottom: 0;
  right: -800px;
  background-color: #E45C5C;
  animation: flyPlus 10s linear infinite;
  -webkit-animation: flyPlus 10s linear infinite;
  transform: rotate(0) translate(200px) rotate(0);
  -webkit-transform: rotate(0) translate(200px) rotate(0);
  -moz-transform: rotate(0) translate(00px) rotate(0);
  -ms-transform: rotate(0) translate(200px) rotate(0);
  -o-transform: rotate(0) translate(200px) rotate(0);
}
.four {
  border-radius: 100%;
  width: 100%;
  height: 100%;
  margin: auto;
  bottom: 0;
  right: 0;
  background-color: #3f5275;
  animation: flyPlus 15s linear infinite;
  -webkit-animation: flyPlus 15s linear infinite;
  transform: rotate(0) translate(200px) rotate(0);
  -webkit-transform: rotate(0) translate(200px) rotate(0);
  -moz-transform: rotate(0) translate(200px) rotate(0);
  -ms-transform: rotate(0) translate(200px) rotate(0);
  -o-transform: rotate(0) translate(200px) rotate(0);
}

@keyframes fly {
  100% {
    transform: rotate(2turn) translate(200px) rotate(-2turn);
    -webkit-transform: rotate(2turn) translate(200px) rotate(-2turn);
    -moz-transform: rotate(2turn) translate(200px) rotate(-2turn);
    -ms-transform: rotate(2turn) translate(200px) rotate(-2turn);
    -o-transform: rotate(2turn) translate(200px) rotate(-2turn);
  }
}
@keyframes flyPlus {
  100% {
    transform: rotate(-2turn) translate(200px) rotate(2turn);
    -webkit-transform: rotate(-2turn) translate(200px) rotate(2turn);
    -moz-transform: rotate(-2turn) translate(200px) rotate(2turn);
    -ms-transform: rotate(-2turn) translate(200px) rotate(2turn);
    -o-transform: rotate(-2turn) translate(200px) rotate(2turn);
  }
}
</style>