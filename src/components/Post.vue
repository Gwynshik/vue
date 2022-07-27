<template>
    <div v-for="post in posts" class="post">
      <div>
        Title: {{post.title}};
      </div>
      <div>
        Body: {{post.body}}
      </div>
      
    </div>
</template>


<script>

export default({
  props: [ 'posts' ],
})
</script>

<style>
.post{
  border: 1px solid black;
  width: 430px;
}
</style>