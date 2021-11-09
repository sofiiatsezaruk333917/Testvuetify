<template>
  <div class="pa-6">
    <!-- <AddTodo @add-todo="AddTodo" />

    <v-list subheader two-line flat>
      <v-list-item-group v-model="settings" multiple>
        <TodoItem
          v-for="(todo, i) in todos"
          :key="todo.id"
          v-bind:index="i"
          v-bind:todo="todo"
          @remove-item="RemoveTodo"
        />
      </v-list-item-group>
    </v-list> -->
  </div>
</template>

<script>
// import TodoItem from "../components/TodoItem";
// import AddTodo from "@/components/AddTodo.vue";

export default {
  name: "List",
  data: () => ({
    todos: [],
  }),

  mounted() {
    fetch("https://jsonplaceholder.typicode.com/todos?_limit=10")
      .then((response) => response.json())
      .then((json) => {
        this.todos = json;
      });
  },
  methods: {
    RemoveTodo(id) {
      this.todos = this.todos.filter((t) => t.id !== id);
    },
    AddTodo(todo) {
      this.todos.push(todo);
    },
  },

  components: {
    // TodoItem,
    // AddTodo,
  },
};
</script>
