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
  background-color: #E45C5C;
  left: -50px;
  top: -100px;
  z-index: 3;
  animation: fly 24s ease infinite;
  transform: rotate(0) translate(80px) rotate(0);
}
.animated .two {
  width: 1500px;
  height: 1800px;
  background-color: #BF9138;
  bottom: -30px;
  left: -80px;
}
.animated .three {
  border-radius: 100%;
  width: 100%;
  height: 100%;
  bottom: 0;
  right: -800px;
  background-color: #AECAC5;
  animation: flyPlus 20s linear infinite;
  -webkit-animation: flyPlus 20s linear infinite;
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
  background-color: #2E73A7;
  animation: flyPlus 30s linear infinite;
  -webkit-animation: flyPlus 30s linear infinite;
  transform: rotate(0) translate(200px) rotate(0);
  -webkit-transform: rotate(0) translate(200px) rotate(0);
  -moz-transform: rotate(0) translate(200px) rotate(0);
  -ms-transform: rotate(0) translate(200px) rotate(0);
  -o-transform: rotate(0) translate(200px) rotate(0);
}

@keyframes fly {
  0%{
    transform: rotate(0) translate(80px) rotate(0);
    -webkit-transform: rotate(0) translate(80px) rotate(0);
    -moz-transform: rotate(0) translate(80px) rotate(0);
    -ms-transform: rotate(0) translate(80px) rotate(0);
    -o-transform: rotate(0) translate(80px) rotate(0);
  }
  50% {
    transform: rotate(2turn) translate(200px) rotate(-2turn);
    -webkit-transform: rotate(2turn) translate(200px) rotate(-2turn);
    -moz-transform: rotate(2turn) translate(200px) rotate(-2turn);
    -ms-transform: rotate(2turn) translate(200px) rotate(-2turn);
    -o-transform: rotate(2turn) translate(200px) rotate(-2turn);
  }
  100%{
    transform: rotate(0) translate(80px) rotate(0);
    -webkit-transform: rotate(0) translate(80px) rotate(0);
    -moz-transform: rotate(0) translate(80px) rotate(0);
    -ms-transform: rotate(0) translate(80px) rotate(0);
    -o-transform: rotate(0) translate(80px) rotate(0);
  }
}
@keyframes flyPlus {
  0%{
    transform: rotate(0) translate(200px) rotate(0);
    -webkit-transform: rotate(0) translate(200px) rotate(0);
    -moz-transform: rotate(0) translate(200px) rotate(0);
    -ms-transform: rotate(0) translate(200px) rotate(0);
    -o-transform: rotate(0) translate(200px) rotate(0);
  }
  50% {
    transform: rotate(-2turn) translate(200px) rotate(2turn);
    -webkit-transform: rotate(-2turn) translate(200px) rotate(2turn);
    -moz-transform: rotate(-2turn) translate(200px) rotate(2turn);
    -ms-transform: rotate(-2turn) translate(200px) rotate(2turn);
    -o-transform: rotate(-2turn) translate(200px) rotate(2turn);
  }
  100%{
    transform: rotate(0) translate(200px) rotate(0);
    -webkit-transform: rotate(0) translate(200px) rotate(0);
    -moz-transform: rotate(0) translate(200px) rotate(0);
    -ms-transform: rotate(0) translate(200px) rotate(0);
    -o-transform: rotate(0) translate(200px) rotate(0);
  }
}

.animated .wrapper {
  height: 100%;
}
.animated .one, .animated .two, .animated .three, .animated .four {
  height: 100%;
}

</style>