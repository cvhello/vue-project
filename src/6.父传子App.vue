<script setup>
import { ref } from 'vue';
// setup语法糖下局部组件无需注册可以使用
import SonCom from './son-com.vue'
const count=ref(100)
setTimeout(() => {
  count.value=200
}, 3000);

</script>

<template>
  <div class="father">
    <h2>父组件App</h2>
    <!-- 1. 绑定属性 -->
    <SonCom :count="count" message="father message"/>
  </div>
</template>

<style scoped>
.father {
    width: 500px;
    height: 500px;background-color: rgb(203, 121, 121);
}
</style>