<template>
  <div class="home">
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <notification result="success" message="La requête a réussi"></notification>

    <grid desk="1 1 1" tablet="2" phone="1 1" class="aa">
      <notification
        result="warning"
        message="La requête a réussi"
      ></notification>
      <p>CHQUD ....</p>
      <notification result="error" message="La requête a réussi"></notification>
      
    </grid>
    <buttonn design="solid red"> Soumettre </buttonn>

  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import Notification from "@/components/Message/Notification.vue";
import Grid from "@/components/Container/Grid.vue";
import Buttonn from '@/components/Buttons/Button.vue';

export default {
  name: "Home",
  components: {
    HelloWorld,
    Notification,
    Grid,
    Buttonn
  },
  data() {
    return {};
  },
  methods: {
    
  },
};
</script>

<style scoped>

</style>
