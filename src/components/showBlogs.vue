<template>
  <div id='show-blogs'>
    <h1>All Blog Articles</h1>
    <input type='text' v-model='search' placeholder='search blogs' />
    <div class='single-blog' v-for='blog in filteredBlogs'>
      <router-link v-bind:to="'/blog/' + blog.id"><h2>{{ blog.title | to-uppercase}}</h2></router-link>
      <article>{{ blog.body }}</article>
    </div>
  </div>
</template>


<script>
import searchMixin from '../mixins/searchMixins';
export default {
  data () {
    return {
      blogs: [],
      search: ''
    }
  },
  methods: {
   
  },
  created() {
    this.$http.get('https://vue-playlist-f2b25-default-rtdb.firebaseio.com/posts.json').then(function(data) {
      return data.json();
    }).then(function(data) {
      var blogsArray = [];
      for (let key in data) {
        data[key].id = key;
        blogsArray.push(data[key]);
      }
      this.blogs = blogsArray
    })
  },
  filters: {
    toUppercase(value) {
      return value.toUpperCase();
    }
  },
  mixins: [searchMixin]
}
</script>

<style>

</style>