<template>
  <div class="todo" v-bind:class="{ completed: todo.completed }">
    <div class="input">
      <input
        type="checkbox"
        v-bind:checked="todo.completed"
        v-on:change="markComplete"
      />
    </div>
    <div class="title">
      {{ todo.title }}
    </div>
    <div class="delete">
      <button @click="$emit('delete-todo', todo.id)">Delete</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  props: ['todo'],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style scoped>
.todo {
  display: flex;
  align-items: center;
  margin-bottom: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid white;
}
.todo.completed .title {
  opacity: 0.5;
}
.todo.completed .title {
  text-decoration: line-through;
}
.input {
  margin-right: 1rem;
}
.title {
  text-align: left;
}
.delete {
  margin-left: auto;
}
</style>
