<template>
  <div class="home">
    <h1>home page</h1>
    <input type="text" v-model="search">
    <p v-if="search">Search name is => {{ search }}</p>
    <div v-for="name in filterNames" :key="name">
      {{ name }}
    </div>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity'
import { computed } from '@vue/runtime-core';

export default {
  setup() {
   let names = ref(['aung aung','kyaw kyaw','mg mg','su su']);
   let search = ref('');
   let filterNames = computed(()=> {
    return names.value.filter((name)=> {
      return name.includes(search.value);
    })
   })


   return {names,search,filterNames}
  }
}
</script>
