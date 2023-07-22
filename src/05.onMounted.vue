<script setup>
//  生命周期函数的使用
// 1.引入函数  
import { onMounted } from 'vue';

// 2.执行函数，传入回调
onMounted(() => {
  console.log('onMounted,组件挂载完毕,mounted执行了1');
})
onMounted(() => {
  console.log('onMounted,组件挂载完毕,mounted执行了22');
})
onMounted(() => {
  console.log('onMounted,组件挂载完毕,mounted执行了33');
})
</script>

<template>
  <div>
    
  </div>
</template>