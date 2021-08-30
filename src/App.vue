<template>
  <div>
    <app-header></app-header>
    <app-ninjas v-bind:ninjas='ninjas'></app-ninjas>
    <app-footer></app-footer>
  </div>
</template>


<script>
import Header from './components/header.vue';
import Footer from './components/footer.vue';
import Ninjas from './components/ninjas.vue';
export default {
  components: {
    'app-header': Header,
    'app-footer': Footer,
    'app-ninjas': Ninjas
  },
  data () {
    return {
      ninjas: [
        {name: 'Ryu', specialty: 'Vue components', show: false},
        {name: 'Crystal', specialty: 'HTML', show: false},
        {name: 'Hitoshi', specialty: 'Click events', show: false},
        {name: 'Tango', specialty: 'Conditionals', show: false},
        {name: 'Kami', specialty: 'Webpack', show: false},
        {name: 'Yoshi', specialty: 'Data', show: false}
      ]
    }
  }
}
</script>

<style>

</style>
