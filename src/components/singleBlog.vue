<template>
  <div id='single-blog'>
    <h1>{{ blog.title }}</h1>
    <article>{{ blog.body }}</article>
    <p>Author: {{ blog.author }}</p>
    <p>Categories:</p>
    <ul>
      <li v-for='category in blog.categories'>{{ category }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      id: this.$route.params.id,
      blog: {}
    }
  },
  created() {
    this.$http.get('https://vue-playlist-f2b25-default-rtdb.firebaseio.com/posts/' + this.id + '.json').then(function(data) {
      return data.json();
    }).then(function(data) {
        this.blog = data;
    })
  }
}
</script>

<style scoped>
</style>