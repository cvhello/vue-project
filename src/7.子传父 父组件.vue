<script setup>
// setup语法糖下局部组件无需注册可以使用
import SonCom from './son-com.vue'
const getMessage = (msg) => {
  console.log(msg);
}


</script>

<template>
  <div class="father">
    <h2>父组件App</h2>
    <!-- 1. 绑定事件 -->
    <SonCom @get-message="getMessage"/>
  </div>
</template>



<style scoped>
.father {
    width: 500px;
    height: 500px;background-color: rgb(203, 121, 121);
}
</style>