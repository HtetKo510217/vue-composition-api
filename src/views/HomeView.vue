<template>
  <div class="home">
    <h1>home page</h1>
    <div v-if="showPost">
      <PostList :posts = "posts"></PostList>
    </div>
    <button @click="showPost = !showPost">Toggle Post</button> <!-- test onUnmounted -->
    <button @click="posts.pop()">Delete post</button> <!-- test onUpdated -->
  </div>
</template>

<script>
import PostList from '../components/PostList'
import { ref } from '@vue/reactivity'

export default {
  components: { PostList },
  setup() {
   let showPost = ref(true)
   let posts = ref([
    {title:'title 1',body:'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo non quibusdam expedita placeat obcaecati saepe in doloribus quasi cum nihil commodi optio, itaque ratione perferendis sed modi consectetur blanditiis omnis?',id:1},
    {title:'title 2',body:'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo non quibusdam expedita placeat obcaecati saepe in doloribus quasi cum nihil commodi optio, itaque ratione perferendis sed modi consectetur blanditiis omnis?',id:2},
    {title:'title 3',body:'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo non quibusdam expedita placeat obcaecati saepe in doloribus quasi cum nihil commodi optio, itaque ratione perferendis sed modi consectetur blanditiis omnis?',id:3},
    {title:'title 4',body:'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo non quibusdam expedita placeat obcaecati saepe in doloribus quasi cum nihil commodi optio, itaque ratione perferendis sed modi consectetur blanditiis omnis?',id:4},
    {title:'title 5',body:'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo non quibusdam expedita placeat obcaecati saepe in doloribus quasi cum nihil commodi optio, itaque ratione perferendis sed modi consectetur blanditiis omnis?',id:5},
   ])


   return {posts,showPost}
  }
}
</script>
