<template>
  <h1>常用 API 的应用</h1>

  原生的：{{ num }}<br>
  调用 myfunc 函数：{{ myfunc() }}<br>
  响应式：{{ num2 }}<br>

  reactive 中的对象：{{ user.name }} -- {{ user.age }}<br>
  {{ name }} -- {{ age }}<br>
  name: <input v-model="name" type="text"><br>
  age: <input v-model="age" type="text"><br>
  <br>
  {{ fullname }}
</template>

<script>
import {computed, reactive, ref} from "vue";

export default {
  name: "ComApi",
  setup() {
    let num = ref(1);
    let myfunc = () => {
      num.value++;
      console.log(num.value);
    };

    let num2 = ref(20);

    const user = reactive({
      name: 'bcu',
      age: '28',
      sex: '男'
    });

    const person = reactive({
      firstname: 'bcu',
      lastname: 'edu'
    });

    let fullname = computed(() => person.firstname + "." + person.lastname);

    return {
      num,
      myfunc,
      num2,
      user,
      name: user.name,
      age: user.age,
      fullname
    };
  }
};
</script>

<style scoped>
/* 样式 */
</style>
