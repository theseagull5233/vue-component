<template>
<div>
  <div class="drawer drawer-right" :class="{'drawer-open':!isShow}">
    <div class="drawer-content-wrapper" :class="{'content-close':isShow,'content-open':!isShow}">
      <div class="drawer-content">
        <p>抽屉抽屉抽屉抽屉</p>
      </div>
    </div>
  </div>
  <a-button type="primary" @click="openDrawer">drawer open</a-button>

</div>
</template>

<script>
import {ref} from "vue"
export default {
name: "Drawer",
  setup(){
  const isShow = ref(true)
  const openDrawer= ()=>{
    isShow.value = !isShow.value
    }
    return{
      openDrawer,
      isShow
    }
  }
}
</script>

<style scoped lang="less">

.drawer {
  position: fixed;
  z-index: 1000;
  height: 100%;
  transition: transform .3s cubic-bezier(.7, .3, .1, 1), height 0s ease .3s, width 0s ease .3s;

  &.drawer-right {
    top: 0;
    right: 0;
    height: 100%;
  }
  .drawer-content-wrapper{
    position: absolute;
    box-shadow: -2px 0 8px rgb(0 0 0 / 15%);
    right: 0;
    height: 100%;

    .drawer-content{
      width: 254px;
      height: 100%;
      z-index: 1;
      overflow: auto;
      background-color: #fff;
      background-clip: padding-box;
      border: 0;
    }
  }
}
.content-open{
  //transform: translateX(0);
  width: 254px;
  transition: width .3s cubic-bezier(.7,.3,.1,1);
}

.content-close{
  //transform: translateX(100%);
  width: 0;
  transition: width .3s cubic-bezier(.7,.3,.1,1);
}

</style>