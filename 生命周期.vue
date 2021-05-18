<template>
  <div>
    
  </div>
</template>
<script>
import{
  onMounted,
} from 'vue'
export default {
  setupt(){
    console.log('setupt1')
    onMounted(() => {
      console.log('onMuounted3')
    })
  },
  beforeCreate() {
    conosle.log('beforeCreated2')
  },
  // 执行顺序 123
}
</script>