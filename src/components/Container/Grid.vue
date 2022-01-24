/* 
    Desktop: > 1008px
    Tablets: 641px to 1007px
    Phone: moins de 640px
*/
<template>
  <div id="grid" :desktop="desk" :tablet="tablet" :sizePhone="phone">
    <p>{{ width }}</p>
    <h1>{{ children }}</h1>
  </div>
</template>

<script>
export default {
  name: "Grid",
  data() {  
    return {
      width: window.innerWidth,
      children: "chaud"
    };
  },
  props: {
      desk: Number,
      tablet: Number,
      phone: Number,
  },
  mounted() {
    this.onResize()
    window.addEventListener("resize", this.onResize);
  },
  unmounted() {
    window.removeEventListener("resize", this.onResize);
    
  },
  methods: {
    onResize() {
      this.width = window.innerWidth;
      window.document.getElementById("grid").style.display = "grid"
      if(this.width < 640) {
          window.document.getElementById("grid").style.gridTemplateColumns = "1fr 1fr 1fr 1fr"
      }
      if(this.width < 641 && this.width < 1007) {
          window.document.getElementById("grid").style.gridTemplateColumns = "1fr 1fr 1fr 1fr"
      }
      if(this.width > 1008) {
          window.document.getElementById("grid").style.gridTemplateColumns = "1fr 1fr 1fr 1fr"
      }
    },
  },
};
</script>

<style>
</style>