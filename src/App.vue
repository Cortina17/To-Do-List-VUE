<template>
  <div id="app">
    <h1>To Do List</h1>
    <ul>
      <li v-for="item in MockTodoItems" :key="item.id">
        <to-do-item :label="item.label" :done="item.done"></to-do-item>
      </li>
    </ul>
  </div>
</template>

<script>

import uniqueId from 'lodash.uniqueid';
import ToDoItem from "./components/ToDoItem.vue"

export default {
  name: 'App',
  components: {
    ToDoItem,
  },
  data() {
    return {
      MockTodoItems: [
        { id: uniqueId('todo-'), label: 'Finish this project', done:false},
        { id: uniqueId('todo-'), label: 'Create a Vue project using CLI', done:true},
        { id: uniqueId('todo-'), label: 'Learn to use the keyboard without looking', done:false},
        { id: uniqueId('todo-'), label: 'Have fun', done:false},
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
