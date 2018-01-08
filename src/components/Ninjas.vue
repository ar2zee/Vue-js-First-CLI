<template>
	<div id="ninjas">
	   <ul>
       <li v-for="ninja in ninjas" v-on:click="ninja.show = !ninja.show">
         <h2>{{ninja.name}}</h2>
         <h3 v-show="ninja.show">{{ninja.speciality}}</h3>
       </li>
     </ul>
     <button v-on:click="deleteNinja">Delete Ninja</button>
  </div>
</template>

<script>
export default {
  props: {
    ninjas: {
        type: Array,
        required: true
      }
    },
  data () {
    return {
      
    }
  },
  methods: {
    deleteNinja: function() {
      this.ninjas.pop()
    }
  },
  //lifecycle hooks
  beforeCreate(){
    console.log('BeforeCreate'); // empty screen
  },
  created() {
    console.log('Created'); // empty screen
  },
  beforeMount(){
    console.log('BeforeMount'); // empty screen
  },
  mounted(){
    console.log('Mounted'); // Page appears only after this step
  },
  beforeUpdate() {
    console.log('beforeUpdate'); // Works only if something change on the page but doesn't affect  page looks
  },
  updated(){
    console.log('Updated'); // page updated but changes apears only after this page 
  }
}
</script>

<style scoped>
  #ninjas {
    width: 100%;
    max-width: 1200px;
    margin: 40px auto;
    padding: 0 20px;
    box-sizing: border-box;
  }
  ul {
    display: flex;
    flex-wrap: wrap;
    list-style-type: none;
    padding: 0;
  }
  li {
    flex-grow: 1;
    flex-basis: 300px;
    text-align: center;
    padding: 30px;
    border: 1px solid #222;
    margin: 10px;
  }
</style>
