<template>
  <div id='add-blog'>
    <h2>Add a new blog post</h2> 
    <form>
      <label>Blog title</label>
      <input type='text' v-model.lazy='blog.title' required />
      <label>Blog Content</label>
      <textarea v-model.lazy='blog.content'></textarea>
      <div id='checkboxes'>
        <label>Ninjas</label>
        <input type='checkbox' value='ninjas' v-model='blog.categories' />
        <label>qizards</label>
        <input type='checkbox' value='qizards' v-model='blog.categories' />
        <label>witches</label>
        <input type='checkbox' value='witches' v-model='blog.categories' />
        <label>cheese</label>
        <input type='checkbox' value='cheese' v-model='blog.categories' />
      </div>
    </form> 
    <div id='preview'>
      <h3>Preview Blog</h3>
      <p>Blog title: {{ blog.title }}</p>
      <p>Blog content:</p>
      <p>{{ blog.content }}</p>
      <p>Blog categories</p>
      <ul>
        <li v-for='category in blog.categories'>{{ category }}</li>
      </ul>
    </div>
  </div>
</template>


<script>
export default {
 
  data () {
    return {
      blog: {
        title: '',
        content: '',
        categories: []
      } 
    }
  },
  methods: {
    
  }
}
</script>

<style>

</style>