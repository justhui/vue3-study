<template>
  <div>
    
  </div>
</template>
<script>
import {
  reactive,
  toRefs,
  computed,
  readonly
} from 'vue'
export default {
  setup(){
    // 非响应式数据
    let obj = {
      a:1
    }
    let obj2 = reactive({
      a:2
    })
    obj2 = readonly(obj2)
    // 响应式数据
    let userinfo = reactive({
      firstname:"you",
      lastname:"yuxi"
    })
    // 计算属性
    let fullname = computed(()=>{
      return userinfo.firstname + '...'+userinfo.lastname
    })
    return {
      ...toRefs(userinfo),
      fullname,
      obj, //原始对象，不具有响应式
      obj2, //通过readonly 后将响应式数据变成非响应式
    }
  }
}
</script>