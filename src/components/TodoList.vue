<template>
  <div>
    <ul>
      <li v-bind:key="todo.id" v-for="todo in todos">
        <Todo
          v-bind:todo="todo"
          v-on:delete-todo="$emit('delete-todo', todo.id)"
        />
      </li>
    </ul>
  </div>
</template>

<script>
import Todo from './Todo';
export default {
  name: 'TodoList',
  components: {
    Todo,
  },
  props: ['todos'],
};
</script>

<style scoped>
div {
  width: 100%;
}
ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}
</style>
