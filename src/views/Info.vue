<template>
  <div class="info">
    <h1>This is an info page.</h1>
    <button type="button" @click="add()">add</button>
  </div>
</template>

<script>
import store from '@/store'
export default {
  name:'Info',
  methods:{
    add(){
      console.log('click add button')
      store.commit('increace')  // 提交vuex事件
    }
  }
}
</script>
