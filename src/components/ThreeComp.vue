
<script>
import {inject} from "vue";

export default {
  name: "ThreeComp",
  setUp(){
    let title= inject('title');
    return{
      title
    }
  }
}
</script>

<template>
  <hr>
  <h3>这是孙子辈组件</h3>
  {{title}}
</template>
<style scoped>

</style>