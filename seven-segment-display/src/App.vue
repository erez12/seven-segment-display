<template>
  <div id="app">
    <digit :value="h1" class="dig" />
    <digit :value="h2" class="dig" />
    <div class="dots blink_me">
      <div class="circle"></div>
      <div class="circle"></div>
    </div>
    <digit :value="m1" class="dig" />
    <digit :value="m2" class="dig" />
    <div class="dots blink_me">
      <div class="circle"></div>
      <div class="circle"></div>
    </div>
    <digit :value="s1" class="dig" />
    <digit :value="s2" class="dig" />
  </div>
</template>

<script>
import Digit from './components/Digit.vue'
function addZero(i) {
    if (i < 10) {
        i = "0" + i;
    }
    return i;
}
export default {
  name: 'app',
  components: {
    Digit
  },
  data: function () {
    return {
      h1:0,
      h2:0,
      m1:0,
      m2:0,
      s1:0,
      s2:0
    };
  },
  mounted: function () {
    setInterval(function (){
      let d = new Date();
      var h = String(addZero(d.getHours()));
      this.h1 = h[0];this.h2 = h[1];
      var m = String(addZero(d.getMinutes()));
      this.m1 = m[0];this.m2 = m[1];
      var s = String(addZero(d.getSeconds()));
      this.s1 = s[0];this.s2 = s[1];
    }.bind(this), 1000);
  }

}
</script>

<style>
#app {
  display: flex;
}
.dig{
  margin-right: 50px;
}
.dots{
  padding-top:110px
}
.circle {
  width: 25px;
  height: 25px;
  background: #990000;
  border-radius: 50%;
  box-shadow: 0px 0px 25px #990000;
  margin-bottom: 40px;
}
.blink_me {
  animation: blinker 0.5s linear infinite;
}

@keyframes blinker {
  50% {
    opacity: 0.2;
  }
}
</style>
