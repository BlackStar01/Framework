/*
    Types: 
    SIMPLE (default),
    TOGGLE

    Design:
    SOLID (default)
    OUTLINE,

    Color: 
    BLUE
    ORANGE
    GREEN
    RED

    Animation Hover
    hover || hoverTop || hoverBottom || hoverLeft || hoverRight

*/

<template>
  <button :class="design">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    design: String,
  },
  data() {
    return {
      red: "#CC3333",
      green: "rgb(9, 133, 81)",
      blue: "rgb(0, 82, 255)",
      orange: "rgb(255, 121, 0)",
    };
  },
  computed: {
    checkColor() {
        let color = "";
        if(this.design.search("red") !== -1 )
        {
            color = this.red;
            return color
        } else if(this.design.search("green") !== -1 )
        {
            color = this.green;
            return color
        } else if(this.design.search("blue") !== -1 )
        {
            color = this.blue;
            return color
        } else if(this.design.search("orange") !== -1 )
        {
            color = this.orange;
            return color
        } 
        return color;
    },
    checkBg() {
        if(this.design.search("solid") === 0)
            return this.checkColor()
        return this.checkColor()
    }
  },
};
</script>

<style scoped>
@import "../../../public/_theme.scss";

button {
  padding: 14px;
  border-radius: 4px;
  color: black;
  cursor: pointer;
  -webkit-transition: ease-out 0.2s;
  -moz-transition: ease-out 0.2s;
  transition: ease-out 0.2s;
}
.red {
  border: 1px solid v-bind(red);
  color: v-bind(red);
}
.orange {
  border: 1px solid v-bind(orange);
  color: v-bind(orange);
}
.green {
  border: 1px solid v-bind(green);
  color: v-bind(green);
}
.blue {
  border: 1px solid v-bind(blue);
  color: v-bind(blue);
}
.solid {
  background-color: v-bind(checkColor);
  color: white !important;
}
.solid:hover {
  filter: brightness(0.8);
}
</style>