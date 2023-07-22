<script setup>
    //原始相应数组
import { ref } from 'vue'

// 1.导入computed
import { computed} from 'vue'


const list = ref([1, 2, 3, 4, 5, 6, 7, 8])


// 2.执行函数 return 计算之后的值  变量接收
const computedList = computed(() => {
  // 做计算,根据一个数据计算得到一个数据
  return  list.value.filter(item=>item>2)
})


setTimeout(() => {
  list.value.push(9,10)
},3000)

</script>

<template>
  <div>
    原始响应式数据--{{ list }}
  </div>
  <div>
    计算属性数组---{{ computedList }}
  </div>
</template>