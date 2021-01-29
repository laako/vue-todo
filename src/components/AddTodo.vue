<template>
  <div>
    <input
      type="text"
      v-model="title"
      name="title"
      v-on:keyup="addTodo"
      placeholder="What shoud be done?"
    />
  </div>
</template>
<script>
export default {
  name: 'AddTodo',
  data() {
    return {
      title: '',
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      if (e.keyCode !== 13) return;
      const newTodoObj = {
        id: Math.floor(Math.random() * 10000),
        title: this.title,
        completed: false,
      };
      this.$emit('add-todo', newTodoObj);
      this.title = '';
    },
  },
};
</script>
<style scoped>
div {
  width: 100%;
  margin-bottom: 1rem;
}
input {
  width: 100%;
  display: block;
  text-align: center;
  height: 2rem;
  border-radius: 0.2rem;
  border: 1px solid black;
}
</style>
