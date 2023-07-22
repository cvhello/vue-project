<!-- 监听单个数据
<script setup>
import { ref, watch } from 'vue'
const count = ref(0)
const setCount = () => {
  count.value++
}

// watch 监听单个数据源
// watch里  ref对象不需要加.value属性
watch(count, (newVal,oldVal) => {
  console.log('count变化',newVal,oldVal);
})

</script>

<template>
  <div>
    <button @click="setCount">+{{ count }}</button>
  </div>
</template> -->



<!-- 监听多个数据 -->
<!-- <script setup>
import { ref,watch } from 'vue'
const count = ref(0)
const changeCount = () => {
  count.value++
}

const name = ref('cp')
const changeName = () => {
  name.value = 'pc'
}
watch([count, name], ([newCount, oldCount],[ newName, oldName]) => {
  console.log('count或者name变化了',[newCount, oldCount],[ newName, oldName]);
})

</script>

<template> -->
  <!-- <div>
    <button @click="changeCount">修改count--{{ count }}</button>
  </div>

  <div>
    <button @click="changeName">修改name--{{ name }}</button>
  </div>
</template> -->


<!-- 立即监听 -->
<!-- <script setup>
import { ref,watch } from 'vue'
const count = ref(0)
// watch立即执行

const setCount = () => {
  count.value++
}

watch(count, (newVal,oldVal) => {
    console.log('count变化了',newVal,oldVal);
},
  {
  immediate:true
})





</script>
<template> -->
  <!-- <div>
    <button @click="setCount">+{{ count }}</button>
  </div>
</template> -->


<!-- 深度监视deep -->

<!-- <script setup>
import { ref,watch } from 'vue'

const state = ref({ count: 0,age:20 })
const changeStateByCount = () => {
  // 直接修改count
  state.value.count++
}
// watch深度监听
watch(state, (newVal, oldVal) => {
  console.log('count变化了');
},
// 开启深度监视
  {
  deep:true
  })
</script>

<template>
  <div>
    {{ state.count }}
    <button @click="changeStateByCount">通过count修改</button>
  </div>
</template>
 -->





 <!-- 想要监听某个特定属性，不监听完 -->
<script setup>
import { ref, watch } from 'vue'
const state = ref({
  name: 'chiaichai',
  age: 18
})

const changeName = () => {
  // 修改name
  state.value.name = 'chaichai-teacher'  
}
const changeAge = () => {
  // 修改age
  state.value.age = 20
}


//  精确监听某个具体属性
// 不开启deep，监听比较深的属性变化时候
// 可以把第一个参数写成函数的写法，返回要监听的具体属性
watch(
  () => state.value.age,
    ()=> {
    console.log('age变化了');
  }
)
//deep性能损耗，尽量不开启

</script>

<template>
  <div>
    当前name ---{{ state.name }}
  </div>
  <div>
    当前age ---{{ state.age }}
  </div>
  <div>
    <button @click="changeName">修改name</button>
    <button @click="changeAge">修改agee</button>
  </div>
</template>
