<script setup>
// 2.通过defineEmits() =>emit(this.$emit)
const emit= defineEmits(['get-message'])

const sendMsg = () => {
    // 触发自定义事件，传数据给父组件
   emit('get-message','this is son message')
}


</script>


<template>
    <div class="son">
        <div>子组件Son</div>
        <button @click="sendMsg">触发自定义事件</button>
    </div>
</template>

<style scoped>
.son {
    width: 400px;
    height: 200px;background-color: rgb(228, 203, 203);
}
</style>