<template>
  <div id="app">
    <div id="header"></div>
    <div id="main-container">
      <h2>Todos</h2>
      <Todos v-bind:todoslist="copyTodos" v-on:delete-todo="deleteTodo" />
    </div>
  </div>
</template>

<script>
//import Search from "@/components/Search";
import Todos from "@/components/Todos";
//import TodoAdd from "@/components/TodoAdd";

export default {
  name: "App",
  components: {
    //Search,
    Todos,
    //TodoAdd,
  },
  methods: {
    deleteTodo(id) {
      console.log(id);
    },
  },
  data() {
    return {
      todos: [
        {
          id: 0,
          title: "Estudiar VUE",
          completed: false,
        },
        {
          id: 0,
          title: "Jugar COD mobile",
          completed: false,
        },
        {
          id: 0,
          title: "Estudiar JS",
          completed: true,
        },
      ],
      copyTodos: [],
    };
  },
  created() {
    this.copyTodos = [...this.todos];
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1.5em;
  padding: 0;
  margin: 0;
}
#main-container {
  border: solid 1px #ccc;
  width: 600px;
  margin: 100px auto;
}
#header {
  background: black;
  padding: 10px;
}
h2 {
  padding: 0 10px;
}
</style>
