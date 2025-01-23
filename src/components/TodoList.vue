<template>
    <TodoItem
      v-for="item in start_todos"
      :key="item.id"
      :id="item.id"
      :title="item.title"
      :completed="item.completed"
      @deleteTodoById="deleteTodoById(item.id)"
      @changeTodos="changeTodos(item.id)"
    ></TodoItem>
  </template>
  
  <script>
  import TodoItem from './TodoItem.vue';
  
  export default {
    components: {
      TodoItem
    },
    props: {
      start_todos: Array,
    },
    emits: [
      'deleteTodoById',
      'changeTodos'
    ],
    methods: {
      deleteTodoById(id) {
        this.$emit('deleteTodoById', id);
      },
      changeTodos(id) {
        this.$emit('changeTodos', id);
      }
    },
  }
  </script>
  
  <style scoped>
  </style>