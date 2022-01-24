<template>
  <div class="home">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <notification result="success" message="message"></notification>
    <grid> Chaud </grid>
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
}
</script>
