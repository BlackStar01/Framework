/*
	Main problem from the CSS.. cannot have many toggle in the same view


    COLOR: Red, Blue, Green, Orange
    TYPE: Rounded or not... Carré by default .... Carré means no border-radius // Not already made
	It can take an content for a message
*/
<template>
  <div class="toggle" :class="design" :type="type">
    <input type="checkbox" id="switch" />
    <label for="switch"></label>
    <p><slot></slot></p>
  </div>
</template>

<script>
export default {
  name: "toggle",
  props: {
    design: String,
	type: String
  },
  data() {
    return {
      red: "#CC3333",
      green: "rgb(9, 133, 81)",
      blue: "rgb(0, 82, 255)",
      orange: "rgb(255, 121, 0)",
      radius: 90,
    };
  },
  computed: {
    checkColor() {
      let color = "";
      if (this.design.search("red") !== -1) {
        color = this.red;
        return color;
      } else if (this.design.search("green") !== -1) {
        color = this.green;
        return color;
      } else if (this.design.search("blue") !== -1) {
        color = this.blue;
        return color;
      } else if (this.design.search("orange") !== -1) {
        color = this.orange;
        return color;
      }
      return color;
    },
    checkType() {
        if(this.type === "rounded")
            return this.radius+"px"
        return "0px"
    }
  },
};
</script>

<style scoped>
@import "../../../public/_theme.scss";
input[type="checkbox"] {
  height: 0;
  width: 0;
  visibility: hidden;
}

label {
  cursor: pointer;
  text-indent: -9999px;
  width: 50px;
  height: 24px;
  background: grey;
  display: block;
  border-radius: v-bind(checkType);
  position: relative;
}

label:after {
  content: "";
  position: absolute;
  top: 4px;
  left: 5px;
  width: 15px;
  height: 15px;
  background: #fff;
  border-radius: v-bind(checkType);
  transition: 0.3s;
}

input:checked + label {
  background: v-bind(checkColor);
}

input:checked + label:after {
  left: calc(100% - 5px);
  transform: translateX(-100%);
}

label:active:after {
  width: 30px;
}
</style>