<template>
  <div class="button">{{value}}</div>
</template>

<script>

export default {
  name: 'ActionButton',
  props: {
    value: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.button{
    padding: 1em;
    text-align: center;
    border: 1px solid;
    margin: 0.5em;
}
</style>
