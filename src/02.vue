<script setup>
// // 1.导入函数
// import { reactive } from 'vue'

// // 2.执行函数，传入一个对象类型的参数  变量接收
// // reactive
// const state = reactive({
//   count: 0
// })

// const setCount = () => {
//   // 组合式api 不用this 直接state.count 拿到变量
//   state.count++
// }




// 1.导入ref函数   由ref函数产生的响应式数据
import { ref } from 'vue'
// 2.执行ref函数，区别: 传入参数[简单数据+对象数据] 变量接收
const count=ref(0)
console.log(count, 'count');

const setCount = () => {
  // 脚本区域修改ref产生的响应式对象数据，必须通过.value属性
// 区别
  count.value++
}

</script>

<template>
  <div>
    <!-- <button @click="setCount">{{ state.count }}</button> -->
  
    <!-- ref函数的  区别-->
    <button @click="setCount">{{ count }}</button>
  </div>
</template>