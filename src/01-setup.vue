<!-- <script>
export default {
  setup() {
    setup里的this 不指向组件实例  指向undefind
    定义数据和函数 必须对象形式return出去
    console.log('setup',this);
    const message = 'this is message'
    const logMessage = () => {
      console.log(message);
    }
    return {
      message,
      logMessage
    }
  },
  beforeCreate() {
    console.log('beforeCreate');
  }
}
</script> -->


<!-- 简单写法 setup 简化代码 -->
<script setup>
const message = 'this is message'
const logMessage = () => {
  console.log(message);
}
</script>

<template>
  <div>
    {{message}}
    <button @click="logMessage">log</button>
  </div>
</template>