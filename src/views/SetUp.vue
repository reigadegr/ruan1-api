

<script>
import SubComp from "@/components/SubComp.vue"
export default {
  name: "SetUp",
  components:{
    SubComp
  },
  methods:{
    add(str){
      console.log(str);
    }
  }
}
</script>
<template>
  这是父组件setup<br>

<SubComp desc="父组件传递给子组件的数据" one="111" two="222">
  <h2>88888</h2>
</SubComp>
</template>

<style scoped>

</style>
