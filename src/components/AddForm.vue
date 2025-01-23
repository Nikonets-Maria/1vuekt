<template>
    <div class="input_elem">
      <input v-on:keyup.enter="addTodo" v-model="title" />
    </div>
  </template>
  
  <script>
  export default {
    emits: ['addTodo'],
    methods: {
      addTodo() {
        this.$emit('addTodo', this.title);
        this.title = '';
      },
    },
    data() {
      return {
        title: ''
      }
    },
  }
  </script>
  
  <style scoped>
  </style>