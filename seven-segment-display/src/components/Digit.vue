<template>

  <div class="digit">
    <div v-bind:class="{ active: sectionA }" class="segment A"></div>
    <div v-bind:class="{ active: sectionB }" class="segment B"></div>
    <div v-bind:class="{ active: sectionC }" class="segment C"></div>
    <div v-bind:class="{ active: sectionD }" class="segment D"></div>
    <div v-bind:class="{ active: sectionE }" class="segment E"></div>
    <div v-bind:class="{ active: sectionF }" class="segment F"></div>
    <div v-bind:class="{ active: sectionG }" class="segment G"></div>
  </div>

</template>

<script>
const Numbers = {
  '0': 'ABCDEF',
  '1': 'BC',
  '2': 'ABGED',
  '3': 'ABCDG',
  '4': 'BCFG',
  '5': 'ACDFG',
  '6': 'ACDEFG',
  '7': 'ABC',
  '8': 'ABCDEFG',
  '9': 'ABCFG',
}

export default {
  name: 'Digit',
  props: {
    value: Number
  },
  computed:{
    sectionA: function (){ return Numbers[this.value].indexOf('A') >= 0; },
    sectionB: function (){ return Numbers[this.value].indexOf('B') >= 0; },
    sectionC: function (){ return Numbers[this.value].indexOf('C') >= 0; },
    sectionD: function (){ return Numbers[this.value].indexOf('D') >= 0; },
    sectionE: function (){ return Numbers[this.value].indexOf('E') >= 0; },
    sectionF: function (){ return Numbers[this.value].indexOf('F') >= 0; },
    sectionG: function (){ return Numbers[this.value].indexOf('G') >= 0; }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .digit{
    position: relative;
  }
  .segment {
    height: 40%;
    width: 13%;
    background-color: #f4f4f4;
    border-radius: 9999px;
    box-shadow: 0px 0px 10px #f4f4f4;
  }
  .active {
    background-color: #4f4f4f;
     box-shadow: 0px 0px 10px #f4f4f4;
  }
  .A {
    position: absolute;
    top: -15%;
    left: 58%;
    transform: rotate(90deg);
  }
  .B {
    position: absolute;
    top: 7%;
    left: 103%;
  }
  .C {
    position: absolute;
    top: 52.5%;
    left: 103%;
  }
  .D {
    position: absolute;
    top: 75%;
    left: 58%;
    transform: rotate(90deg);
  }
  .E {
    position: absolute;
    top: 52.5%;
    left: 13%;
  }
  .F {
    position: absolute;
    top: 7%;
    left: 13%;
  }
  .G {
    position: absolute;
    top: 30%;
    left: 58%;
    transform: rotate(90deg);
  }
</style>
