<template>
  <div id="app">
    <BaseInput 
      :value="inputValue"
      @input="inputValue = $event"
      placeholder="enter something"
      type="text"
      @focus="focusFn"
    ></BaseInput>
    <h1>{{inputValue}}</h1>
    <em>{{msg}}</em>
  </div>
</template>

<script>
import BaseInput from './components/BaseInput.vue'

export default {
  name: 'app',
  components: {
    BaseInput
  },
  data() {
    return {
      inputValue: '',
      msg: ''
    }
  },
  methods: {
    focusFn() {
      window.console.log('parent vue');
    }
  }
}
</script>

<style>

</style>
