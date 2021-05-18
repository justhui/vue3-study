<template>
  <div>
    
  </div>
</template>
<script>
import {
  ref,
  reactive,
  toRefs,
  watchEffect,
  watch
} from 'vue'
export default {
  setup(){
    let data = reactive({
      num:1,
      count:1
    })
    // 刚加载的时候一定会执行一次，后续触发也会执行
    watchEffect(()=>{
      console.log(data.num)
    })
    // 同vue2,能指定具体的监听对象
    watch(data,(newval,oldval)=>{
      conosle.log(data.num)
      conosle.log(newval,oldval)
    })
    setTimeout(()=>{
      data.num++
    },1000)
    return {
      ...toRefs(data)
    }
  }
}
</script>