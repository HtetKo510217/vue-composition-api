<template>
   <h3>{{ post.title }}</h3>
    <p>{{ cutPostBody }}</p>
</template>

<script>
import { computed } from '@vue/runtime-core'
export default {
    props:['post'],
    setup(props) {
        let cutPostBody = computed(()=> {
            return  props.post.body.substring(0,50) + ' ...';
        })
        return {cutPostBody}
    }
}
</script>

<style>

</style>