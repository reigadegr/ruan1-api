
<script>
import {reactive, ref, toRefs, watch, watchEffect} from "vue";

export default {
  name: "WatchDemo",
  setup(){
    const user =reactive({
      a:1,
      b:2
    })
    watch([()=> user.a,()=>user.b],([newA,newB],[oldA,oldB])=>{
      console.log(user.a+'----------'+user.b)
      console.log(newA+'###########'+oldA);
      console.log(newB+'###########'+oldB);
      //只显示user变化前后的类型，不显示数据
      //console.log(newX+'#########'+oldX);
    },{immediate:true})
    watchEffect(()=>{
      console.log(user.a+'----------');
    })
    return {
      ...toRefs(user)
    }
    // let a=ref(1);
    // let b=ref(2);
    //默认监听应用数据的变化
    // watch(()=>{
    //   console.log(a.value+'---------'+b.value);
    // })

    //watch (被监听的对象，监听对象数据发生变化时执行的函数，其他选项)
    //当指明被监听的对象后，仅仅监听这个对象
    //监听多个数据，则需要把数据放到数组
    //可以再箭头函数传入两个参数
    //
    // $1: 被监听数据变化后的值
    //$2: 被监听数据变化之前的值

    // watch([a,b],([newA,oldA],[newB,oldB])=>{
    //   console.log(a.value+'---------'+b.value);
    //   console.log(newA+'###########'+oldA);
    //   console.log(newB+'###########'+oldB);
    // },{Immediate:true})
    // watchEffect(()=>{
    //   console.log(a.value+'---------'+b.value);
    // })
    //
    // return {
    //   a,
    //   b
    // }
  }
}
</script>
<template>
  <h2>侦听器watch() api</h2>
  <button @click="a++">{{a}}</button>
  <button @click="b++">{{b}}</button>
</template>

<style scoped>

</style>