

<script>
import TwoComp from "@/components/TwoComp";
import {provide, ref} from "vue";

export default {
  name: "RootApp",
  components:{
    TwoComp
  },
  // data(){
  //   return{
  //     title:'这是根组件提供的数据'
  //   }
  // },
  //这个方法无法使用this引用data的数据
  // provide:{
  //   title:'abc'
  // }
  //建议
  // provide(){
  //   return{
  //     title:this.title
  //   }
  // }
  setup(){
    let title = ref('这是根组件提供的数据2');

    provide('title',title)
    return{
      title
    }
  }
}
</script>

<style scoped>

</style>

<template>
  <h1>这是根组件</h1>
  {{title}}
  <br>
  <input type="text" v-model="title">
  <TwoComp></TwoComp>
</template>
