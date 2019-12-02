<template>
  <label>
    <input
      :value="value"   
      @input="$emit('input', $event.target.value)"
      v-bind="$attrs"
      v-on="inputListeners"
    >
  </label>
</template>

<script>
export default {
  inheritAttrs: false,
  name: 'BaseInput',
  props: ['value'],
  computed: {
    inputListeners() {
      let vm = this;
      return Object.assign({}, this.$listeners, {
        input: function(event) {
          vm.$emit('input', event.target.value)
        }
      })
    }
  }
}
</script>

<style scoped>

</style>
