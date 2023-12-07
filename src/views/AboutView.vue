<template>
  <div class="about">
    <h3>count:{{data.count}}</h3>
    <h3>double:{{data.double}}</h3>
    <h3><h3>count:{{data.count}}</h3>
      <button @click="add()">自增</button>
    </h3>
  </div>
</template>
<script>
import {computed, reactive} from "vue"
export default {
  name:'AboutView',
  setup(){
    //在setup中定义对象类型变量data
    const data=reactive({
      //data对象的属性
      count:0,
      //使用computed生成第二个对象属性
      double:computed(()=>data.count*2)
    })
    //SETUPding定义函数
    function  add(){
      data.count++;
    }
    //setup,定义的all成员（变量，常量 函数）外界要使用必须导出
    return{
      data,
      add
    }
  }
}
</script>