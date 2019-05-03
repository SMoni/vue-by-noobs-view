<template>
  <div class="todo-item">
    <div class="button" @click="$emit('remove', item.id)">X</div>
    <div class="text">{{ item.text }}</div>
    <!-- <select class="state" v-model="item.state">
      <option value="backlog">Backlog</option>
      <option value="doing">Doing</option>
      <option value="done">Done</option>
    </select>  -->
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: {
    item: {
      type: Object,
      required: true
    }
  }
}
</script>

<style lang="less" scoped>

.todo-item {

  display:     table-row;
  line-height: 1.8rem;

  > * {
    display: table-cell;
    padding: 0 1rem;
  }

  .button {
    cursor:       pointer;
    width:        1.5rem;
    text-align:   center;
    border:       1px solid grey;
    margin-right: 1rem;

    &:hover {
      background-color: grey;
      color:            white;
    }
  }
}
</style>
