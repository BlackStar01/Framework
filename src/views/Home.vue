<template>
  <div class="home">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <notification result="warning" message="La requête a réussi"></notification>

    <grid desk="1 1 1" tablet="1" phone="1">
      <notification result="warning" message="La requête a réussi"></notification>
      <p>CHQUD ....</p>
       <notification result="warning" message="La requête a réussi"></notification>
    </grid>

    <button @click="checkNumber"> Check </button>
    
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Notification from '@/components/Message/Notification.vue'
import Grid from '@/components/Container/Grid.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld, Notification, Grid
  },
  data() {
    return {
      
    };
  },
  methods: {
    checkNumber() {
      let e = window.document.getElementsByClassName("grid")
      for (let i = 0; i < e.length; i++) {
        console.log(e[i])
      }
      return console.log()
    }
  }
  
}
</script>
