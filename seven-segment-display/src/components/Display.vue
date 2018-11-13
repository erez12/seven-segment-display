<template>
  <div class="display">
    <digit :value="h1" class="dig" />
    <digit :value="h2" class="dig" />
    <digit :value="m1" class="dig" />
    <digit :value="m2" class="dig" />
    <digit :value="s1" class="dig" />
    <digit :value="s2" class="dig" />
  </div>
</template>

<script>
import Digit from './Digit.vue'
function addZero(i) {
    if (i < 10) {
        i = "0" + i;
    }
    return i;
}
export default {
  name: 'Display',
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
      this.h1 = parseInt(h[0]);this.h2 = parseInt(h[1]);
      var m = String(addZero(d.getMinutes()));
      this.m1 = parseInt(m[0]);this.m2 = parseInt(m[1]);
      var s = String(addZero(d.getSeconds()));
      this.s1 = parseInt(s[0]);this.s2 = parseInt(s[1]);
    }.bind(this), 1000);
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.display{
    display: flex;
    border: 1px solid;
    width: 100%;
    /* padding: 2px; */
}
.dig{
    margin-right: 15px;
    height:60px;
    width: 30px;
}
</style>
