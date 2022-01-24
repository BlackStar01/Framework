<template>
  <div id="notification" :class="result">
      <box-icon :name='iconName' type='solid' :color='iconBg' class="icon"></box-icon>
      <small> {{message}} </small>
  </div>
</template>

<script>
module.exports = {
    name: "Notification",
    props: {
        message: String,
        result: String
    },
    computed: {
        iconBg: function() {
            switch (this.result) {
                case "success":
                    return "#098551";
  
                case "error":
                    return "#cc3333";
                    
                case "warning":
                    return "rgb(255, 121, 0)"
                default:
                    break;
            }
        },
        iconName: function() {
            switch (this.result) {
                case "success":
                    return "check-circle";
  
                case "error":
                    return "error-alt";
                    
                case "warning":
                    return "error"
                default:
                    break;
            }
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../../../public/_theme.scss";

#notification {
    position: relative;
    width: 100%;
    border-radius: 5px;
    background-color: #f1f1f1;
    padding: 15px;
}

#notification[class="success"] {
    border: 1px solid $green;
}
#notification[class="error"] {
    border: 1px solid $red;
}
#notification[class="warning"] {
    border: 1px solid $orange;
}
.success {
    color: $green;
}
.error {
    color: $red;
}
.warning {
    color: $orange;
}
.icon {
    margin: 0px 10px;
    position: absolute;
    top: 50%;
    left: 20px;
    transform: translate(-15px, -50%);
}
small {
    padding: 15px 50px;
}
</style>