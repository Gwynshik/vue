<template>
<div  v-for="post in posts" class="title">
    Title: {{post.title}}    
</div>
</template>


<script>
export default({
    props: [ 'posts' ],
})
</script>

<style>
.title{
  border: 1px solid black;
}
</style>