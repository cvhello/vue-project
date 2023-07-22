<script setup>
const props= defineProps({
    message: String,
    count:Number,
})
 console.log(props,'props');
</script>

<template>
    <div class="son">
        <h3>子组件Son</h3>
        <div>
            父组件传入的数据-{{ message }}----{{ count }}
        </div>
    </div>
</template>

<style scoped>
.son {
    width: 400px;
    height: 200px;background-color: rgb(228, 203, 203);
}
</style>