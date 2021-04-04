<template>
  <div>
    <h5>内联无限循环进度条</h5>
    <p class="mui-progressbar mui-progressbar-infinite"></p>
  </div>
</template>

<script>
export default {
name: "ProgressBar"
}
</script>

<style scoped>
.mui-progressbar{
  position: relative;
  display: block;
  overflow: hidden;
  border-radius: 8px;
  width: 90%;
  height: 10px;
  -webkit-transform-origin: center top;
  transform-origin: center top;
  vertical-align: middle;
  background: #b6b6b6;
  -webkit-transform-style: preserve-3d;
  transform-style: preserve-3d;
}

.mui-progressbar.mui-progressbar-infinite::before {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
  -webkit-transform: translate3d(0,0,0);
  transform: translate3d(0,0,0);
  -webkit-transform-origin: left center;
  transform-origin: left center;
  -webkit-animation: mui-progressbar-infinite 1s linear infinite;
  animation: mui-progressbar-infinite 1s linear infinite;
  background: #007aff;
}
@keyframes mui-progressbar-infinite {
  0% {
    transform: translate3d(-50%,0,0) scaleX(.5)
  }

  100% {
    transform: translate3d(100%,0,0) scaleX(.5)
  }
}
</style>