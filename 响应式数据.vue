<template>
  <div></div>
</template>

<script>
import {
  ref,
  reactive,
  toRefs
} from 'vue'
export default {
  setup() {
    // ref 定义响应式数据 简单类型
    // reactive 定义响应式数据 定义复杂类型 对象
    let title = ref("hello world");
    let userinfo = reactive({
      username:"张三",
      age:20
    })
    // 获取reactive里面定义的数据
    let getUserName = ()=>{
      conosle.log('username',userinfo.username)
    }
    // 获取ref里面定义的数据
    let getTitle = ()=>{
      console.log('title',title.value)
    }

    // 修改ref里面定义的数据
    let setTitle = () =>{
      title.value = 'vue3'
    }
    // 修改reactive里面定义的数据
    let setUserName = ()=>{
      userinfo.username = '李四'
    }

    // toRefs 使对象解构具有响应式
    let article = reactive({
      name:"vue3",
      length:100
    })
    return {
      title,
      userinfo,
      getTitle,
      getUserName,
      setTitle,
      setUserName,
      // ...article //不具有动态响应式
      ...toRefs(article) // 具有响应式
    }
  },
};
</script>