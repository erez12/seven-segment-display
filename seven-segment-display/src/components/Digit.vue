<template>

  <div class="digit">
    <div v-if="sectionA" class="segment A"></div>
    <div v-if="sectionB" class="segment B"></div>
    <div v-if="sectionC" class="segment C"></div>
    <div v-if="sectionD" class="segment D"></div>
    <div v-if="sectionE" class="segment E"></div>
    <div v-if="sectionF" class="segment F"></div>
    <div v-if="sectionG" class="segment G"></div>
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
    height:285px;
    width: 155px;
  }
  .segment {
    height: 125px;
    width: 15px;
    background-color: #990000;
    border-radius: 9999px;
    box-shadow: 0px 0px 25px #990000;
  }

  .A {
    position: absolute;
    top: -45px;
    left: 90px;
    transform: rotate(90deg);
  }
  .B {
    position: absolute;
    top: 20px;
    left: 160px;
  }
  .C {
    position: absolute;
    top: 150px;
    left: 160px;
  }
  .D {
    position: absolute;
    top: 215px;
    left: 90px;
    transform: rotate(90deg);
  }
  .E {
    position: absolute;
    top: 150px;
    left: 20px;
  }
  .F {
    position: absolute;
    top: 20px;
    left: 20px;
  }
  .G {
    position: absolute;
    top: 85px;
    left: 90px;
    transform: rotate(90deg);
  }
</style>
