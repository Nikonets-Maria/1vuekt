<template>
    <div class="input_elem">
      <input v-on:keyup.enter="addTodo" :value ="title" @input="handleInput"/>
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
      handleInput(){
        this.title = event.target.value;
      }
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