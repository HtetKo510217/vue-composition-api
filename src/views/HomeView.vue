<template>
  <div class="home">
    <h1>home page</h1>
    <p>My name is {{ name }} and age is {{ age.age }}</p>
    <button @click="changeName">change name</button>
    <button @click="changeAge">change Age</button>
  </div>
</template>

<script>
import { reactive, ref } from '@vue/reactivity'

export default {
  setup() {
    let name = ref('htetko');
    let age = reactive({age:24});
    console.log(age.age);
    let changeName = () => {
      name.value = 'change name'
    }
    let changeAge = () => {
      age.age = 40;
    }
    return {name,age,changeName,changeAge}
  }
}
</script>
