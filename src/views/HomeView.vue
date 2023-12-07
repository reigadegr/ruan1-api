<template>
  <div class="home">
  <h3>count:{{count}}</h3>
    <h3>double:{{double}}</h3>
    <h3><button @click="add()">
      +1按钮
    </button>
    </h3>
  </div>
</template>

<script>
//option配置方式
export default {
  name: 'HomeView',
  data(){
    return{
      count:1
    }
  },
  computed:{
    double(){
      return this.count*2;
    }
  },
  methods:{
    add(){
      this.count++;
    }
  }
}
</script>
