<template>
  <div>
    <mast-head/>

    <input-todo v-on:add-todo="addTodo"/>

    <item-todo 
      v-for="(todo, i) in todos" 
      v-bind:key="i"
      v-bind="todo"
      v-on:remove-todo="removeTodo(i)"
    />
    
  </div>
</template>

<script>
  import MastHead from './components/MastHead';
  import InputTodo from './components/InputTodo';
  import ItemTodo from './components/ItemTodo';

  export default {
    name: 'App',
    data() {
      return {
          todos: [ ]
      }
    },
    methods: {
      addTodo(todo) {
        this.todos.push({ todo, date: new Date() } );
      },
      removeTodo(index) {
        this.todos.splice(index, 1);
      }
    },
    components: {
      MastHead,
      InputTodo,
      ItemTodo
    }
  };
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Open+Sans&display=swap');

  body {
    margin: 0;
    padding: 0;
    font-family: 'Open Sans', sans-serif;
  }
</style>
