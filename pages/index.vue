<template>
  <div>
    <p>{{user.name}}</p>
    <AddTodo @submit="addTodo"/>
    <TodoList :todos="todos"/>
  </div>
</template>

<script>
import AddTodo from "@/components/AddTodo";
import TodoList from "@/components/TodoList";

export default {
  components: {
    AddTodo,
    TodoList
  },
  computed: {
    user() {
      return this.$store.state.currentUser;
    }
  },
  created() {
    console.log("API_KEY:", process.env.API_KEY);
  },
  data(){
    return {
      todos: []
    }
  },
  methods: {
    addTodo(title) {
      this.todos.push({
        title
      });
    }
  }
};
</script>

<style>
</style>