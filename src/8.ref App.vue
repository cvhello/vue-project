<script setup>
import { onMounted, ref } from 'vue';
import TestCom from './test-com.vue';


// 1.调用ref函数  => ref对象
const h1Ref = ref(null)
const comRef=ref(null)

// 组件挂载完毕才可以获取
onMounted(() => {
  console.log(h1Ref.value);


  // 默认情况下<script setup>语法糖下组件内部的属性
  // 和方法是不开放给父组件访问的，
  // 可以通过defineExpose编译宏指定哪些属性和方法是允许访问
  console.log(comRef.value);

})


</script>

<template>
  <!-- 2. 通过ref标识绑定ref对象 -->
    <h1 ref="h1Ref">我是dom元素h1</h1>
    <TestCom ref="comRef"/>
</template>