<template>
  <div>
    <h1>pls fill out form</h1>

    <form>

      <div id='form-header'>
        <slot name='form-header'></slot>
      </div>

      <div id='form-fields'>
        <slot name='form-fields'></slot>
      </div>
      
      <div id='form-controls'>
        <slot name='form-controls'></slot>
      </div>
      
      <div id='useful-links'>
        <ul>
          <li><a href='#'>L1</a></li>
          <li><a href='#'>L2</a></li>
          <li><a href='#'>L3</a></li>
          <li><a href='#'>L4</a></li>
        </ul>
      </div>

    </form>
  </div>
</template>

<script>
export default {
  components: {

  },
  data() {
    return {
      title: 'dynamo'
    }
  },
  methods: {

  }
}
</script>

<style scoped>

</style>