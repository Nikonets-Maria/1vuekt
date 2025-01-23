<template>
    <div
      class="todo_card"
      :style="{ backgroundColor: completed ? 'green' : 'red' }"
      @dblclick="deleteTodoById"
      @click="changeTodos"
    >
      <h2>{{ title }}</h2>
      <!-- <p>{{ id }}</p> -->
    </div>
  </template>
  
  <script>
  export default {
    props: {
      id: Number,
      title: String,
      completed: Boolean,
    },
    emits: [
      'deleteTodoById',
      'changeTodos'
    ],
    methods: {
      deleteTodoById() {
        this.$emit('deleteTodoById', this.id);
      },
      changeTodos() {
        this.$emit('changeTodos', this.id);
      }
    },
  }
  </script>
  
  <style scoped>
  </style>