<template>
  <div id="app">
    <div class="calculator center">
      <display/>

      <div class="actions row">
        <div class="numbers col">
          <div class="row">
            <ActionButton value='7'/><ActionButton value='8'/><ActionButton value='9'/>
          </div>
          <div class="row">
            <ActionButton value='4'/><ActionButton value='5'/><ActionButton value='6'/>
          </div>
          <div class="row">
            <ActionButton value='1'/><ActionButton value='2'/><ActionButton value='3'/>
          </div>
          <div class="row">
            <ActionButton value='.'/><ActionButton value='0'/><ActionButton value='DEL'/>
          </div>
        </div>

        <div class="operations">
          <div class="col">
            <ActionButton value='/'/><ActionButton value='x'/><ActionButton value='-'/><ActionButton value='+'/><ActionButton value='='/>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Display from './components/Display.vue'
import Digit from './components/Digit.vue'
import ActionButton from './components/ActionButton.vue'
export default {
  name: 'app',
  components: {
    Display,
    Digit,
    ActionButton
  }
}
</script>

<style>
  .center {
    margin: auto;
    width: 300px;
    border: 3px solid #73AD21;
    padding: 10px;
  }
  .calculator{
    display: flex;
    flex-direction: column;
  }
  .row{
    display: flex;
    flex-direction: row;
  }
  .col{
    display: flex;
    flex-direction: column;
  }
  .actions{
    padding-top: 0.5em
  }
  .numbers .row{
    height: 5.3em;
  }
</style>