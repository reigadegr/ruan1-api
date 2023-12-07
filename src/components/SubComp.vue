<script>
export default {
  name: "SubComp",
  data() {
    return {
      msg: 'this is msg',
    }
  },
  props: {
    one: {
      type: String
    },
    two: {
      type: String
    }
  },
  //props 父组件传递子组件的数据
  //context 上下文
  //setup(props，context) {
  setup(props, {attrs,slots,emit}) {
    console.log('setup......');
    //console.log(this);setup执行时，this还没被创建
    console.log(props.one + props.two);
    //context.attrs直接获取父组件传递给子组件的数据
    console.log(attrs.desc);
    //context.slot
    console.log(slots.default());
    //context.emit实现子组件向父组件发送数据
    emit('myapp','子组件向父组件发送的数据');
  },
  beforeCreate() {
    console.log('before create $$$');
  },
  create() {
    console.log('create $$$');
    console.log(this.msg);
    console.log(this);
  }
}

</script>
<template>
  这是子组件subcomp<br>
  <slot>999999999999</slot>
</template>
<style scoped>

</style>
