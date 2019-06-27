<template>
  <div class="about">
    <h1>This is an about page.</h1>
    <p>点击次数：{{msg}}</p>
  </div>
</template>

<script>
import store from '@/store';
export default {
  name:'about',
  data(){
    return {
      msg: store.state.count
    }
  }
}
</script>
