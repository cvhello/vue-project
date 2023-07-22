<script setup>
import { ref } from 'vue';

const name = ref('test name')
const setName = () => {
    name.value='test new name'
}
// 显示暴露组件内部的属性和方法
defineExpose({
    name,setName
})

</script>


<template>
    <div class="son">
        <div>我是test组件</div>
      
    </div>
</template>

<style scoped>

</style>