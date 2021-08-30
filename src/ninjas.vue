<template>
  <div>
    <h1>List of ninjas</h1>
    <ul>
      <li v-for='ninja in ninjas'>{{ ninja }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data () {
    return {
      ninjas: ['Yoshi', 'mario', 'ryu']    
    }
  },
 
}
</script>

<style>
h1 {
    color: green;
}

</style>
