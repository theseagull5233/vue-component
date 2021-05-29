<template>
<div style="padding: 10px">
  <div style="text-align: center">
    <p style="font-size: 20px;font-weight: bold">
      web 实例 demo
    </p>
  </div>
<!--  无限循环进度条-->
  <ProgressBar/>
  <a-divider/>
<!--  抽屉的实现-->
  <Drawer/>
  <a-divider/>
<!--  transition的用法-->
  <BoxTransition/>
  <a-divider/>
<!--  canvas定位图标-->
  <PositionPic></PositionPic>
</div>
</template>

<script>
import ProgressBar from "@/components/ProgressBar";
import Drawer from "@/components/Drawer";
import BoxTransition from "@/components/BoxTransition";
import PositionPic from "@/components/PositionPic";

export default {
  name: 'App',
  components: {
    PositionPic,
    BoxTransition,
    Drawer,
    ProgressBar,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  color: #2c3e50;
  margin-top: 60px;
}
</style>
