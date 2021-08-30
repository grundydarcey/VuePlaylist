<template>
  <div id='show-blogs'>
    <h1>All List Articles</h1>
    <input type='text' v-model='search' placeholder='search blogs' />
    <div class='single-blog' v-for='blog in filteredBlogs'>
      <h2 v-rainbow>{{ blog.title | to-uppercase}}</h2>
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
    this.$http.get('https://jsonplaceholder.typicode.com/posts').then(function(data) {
      this.blogs = data.body.slice(0, 10);
    })
  },
  mixins: [searchMixin],
  filters: {
    toUppercase(value) {
      return value.toUpperCase();
    }
  },
  directives: {
    'rainbow': {
      bind(el, binding, vnode) {
        el.style.color = '#' + Math.random().toString(16).slice(2,8)
      }
    }
  }
}
</script>

<style>

</style>