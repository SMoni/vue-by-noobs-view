<template>
  <div id="app">
    <img src="@/assets/softwerkskammer.png">
    <HelloWorld msg="Hello World... OMG!!!OneOneEleven!!"/>
    <todo-list />
  </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue'
import TodoList   from '@/components/Todo/List.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    TodoList
  }
}
</script>

<style lang="less">

body {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 14px;
}

.todo-list {
  margin-left: 3rem;
}

</style>
