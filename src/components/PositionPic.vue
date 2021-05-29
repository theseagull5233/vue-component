<template>
<div>
  <div>
    canvas定位图片
  </div>
  <div>
    <canvas id="cv" width="100" height="100"></canvas>
  </div>
</div>
</template>

<script>
import {onMounted} from 'vue'
import corpLogo from '../assets/position/map_position_default.png'
export default {
name: "PositionPic",
  setup(){

  const init = ()=>{
      //1. 获取canvas元素
      let cv = document.getElementById("cv");
      //2. 获取2D上下文
      let ctx = cv.getContext('2d');
      //3. 新建一个Image对象
      let img = new Image();
      //4. 设置Image的src
      img.src = corpLogo
      //5. 确定Image加载完毕后将Image画到canvas上
      img.onload = () => {
        ctx.drawImage(img, 0, 0, 100, 100);
        ctx.beginPath();
        ctx.arc(70, 15, 10, 0, 2 * Math.PI);
        ctx.fillStyle = "red";
        ctx.fill();
        ctx.stroke();
        ctx.font = "10px";
        ctx.fillStyle ="black"
        ctx.fillText("10", 64, 18);

      }

  }

    onMounted(()=>{
      init()
    })
  }
}
</script>

<style scoped>

</style>