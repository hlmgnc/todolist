<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from './components/Todos'
import AddTodo from './components/AddTodo'
export default {
  name: 'app',
  components: {
    Todos,
    AddTodo,
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'tidy the room',
          completed: false,
        },
        {
          id: 2,
          title: 'clean the car',
          completed: true,
        },
        {
          id: 3,
          title: 'go to shopping',
          completed: false,
        },
        {
          id: 4,
          title: 'cook some meal',
          completed: true,
        },
      ],
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id)
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo]
    },
  },
}
</script>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans',
    'Helvetica Neue', sans-serif;
}
.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover {
  background: #666;
}
</style>
