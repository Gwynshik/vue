<template>
<div class="app">
  <div class="wrapper-post">
    <Post v-if="post =! 0" :posts="posts" />
  </div>
  <button type="button" @click="load" class="btn"  >Load</button>
</div>

</template>

<script>
import Post from './components/Post.vue'

export default {
  name: 'App',
  components:{
    Post
  },
  data(){
    return{
      countPage: 0,
      posts: []
    }
  },
  methods: {
    async load(){
      this.countPage++;
      console.log(this.countPage);
      const loadedPost = await fetch(`https://jsonplaceholder.typicode.com/posts?_page=${this.countPage}_limit=12`).then(response => response.json());
      console.log(loadedPost);
      this.posts = this.posts.concat(loadedPost);
    }
  }
}
  

</script>

<style>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.app{
  display: flex;
  flex-direction: column;
  height: 100vh;
  width: 100vw;
  align-items: center;
  background-color: #FFF9C4;
}
.wrapper-post{
  display: flex;
  padding: 30px;
  gap: 15px;
  flex-wrap: wrap;
}
.btn{
  position:fixed; 
  bottom: 1rem;
  width: 200px;
  height: 50px;
}
</style>
