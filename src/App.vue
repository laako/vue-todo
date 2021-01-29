<template>
  <div id="app">
    <h1>Todo app with Vue</h1>
    <AddTodo v-on:add-todo="addTodo" />
    <TodoList v-bind:todos="todos" v-on:delete-todo="deleteTodo" />
  </div>
</template>

<script>
import AddTodo from './components/AddTodo.vue';
import TodoList from './components/TodoList.vue';
export default {
  components: { TodoList, AddTodo },
  name: 'App',
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'Go workout',
          completed: false,
        },
        {
          id: 2,
          title: 'Do laundry',
          completed: false,
        },
        {
          id: 3,
          title: 'Cook food',
          completed: false,
        },
        {
          id: 4,
          title: 'Clean up room',
          completed: false,
        },
        {
          i: 5,
          title: 'Finish work',
          completed: false,
        },
      ],
    };
  },
  methods: {
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    },
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
  },
};
</script>

<style>
html,
body {
  background: black;
  color: white;
}
* {
  font-family: Arial, Helvetica, sans-serif;
}
#app {
  margin: 0 auto;
  max-width: 600px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
