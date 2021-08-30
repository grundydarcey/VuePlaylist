<template>
  <div v-theme="'narrow'" id='show-blogs'>
    <h1>All Blog Articles</h1>
    <div class='single-blog' v-for='blog in blogs'>
      <h2 v-rainbow>{{ blog.title | to-uppercase}}</h2>
      <article>{{ blog.body | snippet }}</article>
    </div>
  </div>
</template>


<script>
export default {
  data () {
    return {
      blogs: []
    }
  },
  methods: {
   
  },
   created() {
      this.$http.get('https://jsonplaceholder.typicode.com/posts').then(function(data) {
        this.blogs = data.body.slice(0, 10);
      })
    }
}
</script>

<style>

</style>