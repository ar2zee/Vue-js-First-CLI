<!-- <template>
  <div>
    <h1>{{title}}</h1>
    <ninjas></ninjas>
  </div>
</template>

<script>
import Ninjas from './Ninjas.vue'  

export default {
  components: {
    'ninjas':Ninjas
  },
  data () {
    return {
      title: 'My first Vue App'
    }
  }
}
</script>

<style scoped>
  h1{
    color: purple;
  }
</style>  -->

<template>
  <div>
    <app-header v-bind:title="title" v-on:changeTitle="updateTitle($event)"></app-header>
    <app-ninjas v-bind:ninjas="ninjas"></app-ninjas>
    <app-footer v-bind:title="title"></app-footer>
  </div>
</template>

<script>
 import Header from './components/Header.vue'
 import Footer from './components/Footer.vue'
 import Ninjas from './components/Ninjas.vue'

export default {
  components: {
    'app-header': Header,
    'app-footer': Footer,
    'app-ninjas': Ninjas,
  },
  data () {
    return {
      ninjas: [
        {name: 'Artur', speciality: 'Vue Component', show: false},
        {name: 'Ryu', speciality: 'Html', show: false},
        {name: 'Hitoshi', speciality: 'CSS', show: false},
        {name: 'Tango', speciality: 'JS', show: false},
        {name: 'Kami', speciality: 'Webpack', show: false},
        {name: 'Yoshi', speciality: 'PHP', show: false},
      ],
      title: "Vue Ninjas",
    }
  },
  methods: {
    updateTitle: function(updatedTitle) {
      this.title = updatedTitle
    }
  }
}
</script>

<style >

</style>