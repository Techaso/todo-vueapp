<template>
  <div id="app">
    <h1 style="color:green;">Create Your To-Do List</h1>
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <todo-list v-bind:todos="todos"></todo-list>
    <create-todo v-on:create-todo="addTodo"></create-todo>
  </div>
</template>

<script>
import TodoList from './components/TodoList'
import CreateTodo from './components/CreateTodo';
import "semantic-ui-css/semantic.min.css";

export default {
  name: 'App',
  components: {
    TodoList,
    CreateTodo,    
  },
  data() {
        return {
            todos: [
            {
              title: 'Market',
              project: 'Buy Maggi packets',
              done: false,
            }]
        }
    },
    methods:{
      addTodo(data) {
        console.log('app.vue file ', data)
        this.todos.push({
          title: data.title,
          project: data.project,
          done: data.done
      });
    }
    }
    
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body {
  background-image: url("./assets/img/bg.png");
}
</style>
