<template>
  <AddForm @addTodo="addTodo" />
  <TodoList
    :start_todos="start_todos"
    @deleteTodoById="deleteTodoById"
    @changeTodos="changeTodos"
  />
</template>

<script>
import AddForm from './components/AddForm.vue';
import TodoList from './components/TodoList.vue';

export default {
  components: {
    AddForm,
    TodoList
  },
  data() {
    return {
      start_todos: [
        { id: 1, title: 'Помыть руки', completed: true },
        { id: 2, title: 'Сделать зарядку', completed: false },
        { id: 3, title: 'Наконец изучить React', completed: true }
      ],
    }
  },
  methods: {
    addTodo(title) {
      this.start_todos.push({
        id: Date.now(),
        title: title,
        completed: false
      });
    },
    // changeTodos(id){ 
    //     console.log('changeTodos'+id) 
    //     let findTodo = this.start_todos.find(todo => todo.id === id) 
    //     findTodo.completed != findTodo.completed 
    //   }, 
    changeTodos(id) {
      // let findTodo = this.start_todos.find(todo => todo.id === id)
      // findTodo.completed != todo.completed 

      this.start_todos = this.start_todos.map(todo => {
        if (todo.id === id) {
          return { ...todo, completed: !todo.completed };
        }
        return todo;
      });
    },
    deleteTodoById(id) {
      this.start_todos = this.start_todos.filter(todo => todo.id !== id);
    },
  }
}
</script>

<style scoped>
</style>