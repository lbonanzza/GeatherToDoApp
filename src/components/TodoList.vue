<template>
  <div>
    <ul>
      <TodoItem
        v-for="todo of todos"
        :key="todo.id + 'label'"
        v-bind:todo="todo"
        @remove-todo="removeTodo"
      />
    </ul>
  </div>
</template>


<script>
import TodoItem from "./TodoItem";
export default {
  props: ["todos"],
  name: "TodoList",
  components: {
    TodoItem
  },
  methods: {
    removeTodo(id) {
      this.$emit("remove-todo", id);
    }
  }
};
</script>

<!--<style scoped>-->
<!--  ul {-->
<!--    list-style: none;-->
<!--    margin: 11px;-->
<!--    padding: 11px;-->
<!--    align-content: center;-->
<!--  }-->
<!--</style>-->