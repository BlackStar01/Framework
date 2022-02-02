
<template>
  <div class="grid" :desktop="desk" :tablet="tablet" :phone="phone">
    <slot></slot>
  </div>
</template>
  
<script>
export default {
  name: "Grid",
  data() {
    return {
      width: window.innerWidth,
    };
  },
  props: {
    desk: String,
    tablet: String,
    phone: String,

  },

  mounted() {
    this.onResize();
    window.addEventListener("resize", this.onResize);
  },
  unmounted() {
    window.removeEventListener("resize", this.onResize);
  },
  methods: {
    nbrCol(e) {
      if (e === "") {
        console.log("An error occured...");
      } else {
        let result = "";
        for (let i = 0; i < e.split(" ").length; i++) {
          result += e.split(" ")[i] + "fr ";
        }
        return result;
      }
    },
    onResize() {
      this.width = window.innerWidth;
      for (let index = 0; index < window.document.getElementsByClassName("grid").length; index++) {
        window.document.getElementsByClassName("grid")[index].style.display = "grid";
      if (this.width < 640) {
        window.document.getElementsByClassName("grid")[index].style.gridTemplateColumns =
          this.nbrCol(this.phone);
      }
      if (this.width > 641 && this.width < 1007) {
        window.document.getElementsByClassName("grid")[index].style.gridTemplateColumns =
          this.nbrCol(this.tablet);
      }
      if (this.width > 1008) {
        /* console.log(this.nbrCol(this.desk)); */
        window.document.getElementsByClassName("grid")[index].style.gridTemplateColumns =
          this.nbrCol(this.desk);
      }
        
      }
    
      
    },
  },
};
</script>

<style>
</style>