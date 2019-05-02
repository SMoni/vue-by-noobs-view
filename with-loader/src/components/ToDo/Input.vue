<template>
  <input class="todo-input" type="text" :value="value" v-on="listeners" />
</template>

<script>
export default {
  name: 'TodoInput',
  props: {
    value: {
      type: String,
      default: ''
    }
  },
  computed: {
    listeners () {
      return {
        ...this.$listeners,
        input: event => this.$emit('input', event.target.value)
      }
    } 
  } 
}
</script>

<style lang="less" scoped>

.todo-input {
  font-size:     1rem;
  width:         30rem;
  margin-bottom: 1rem;
}

</style>

