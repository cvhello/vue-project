<script setup>
import Msg from './room-msg-comment.vue'
import { provide, ref } from 'vue';
// 组件嵌套关系
// RoomPage->RoomMsgItem=>RoomMsgComment


// 1.顶层组件提供数据
provide('date-key', '顶层的信息 this is romm data')

// 传递响应式数据
const count = ref(0)
const setCount = () => {
  count.value++
}
provide('count-key', count)
setTimeout(() => {
  count.value=100
},3000)

// 传递方法(谁的数据 谁改动)
provide('setCount-key',setCount)



</script>

<template>
  <div class="page">
    顶层组件
    <Msg />
  </div>
</template>

<style scoped>
.page {
  width: 800px;
  height: 800px;
  background-color: #f7e9e9;
}

div {
  padding: 20px 0;
}
</style>