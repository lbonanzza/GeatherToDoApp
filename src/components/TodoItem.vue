<template>
  <li v-bind:class="{done: todo.completed}">
    <span>
      <div>
        <v-checkbox
          class="checkbox"
          v-model="checkbox2"
          :label="`${todo.title}`"
          @change="todo.completed = !todo.completed"
        ></v-checkbox>
      </div>

      <div class="my-2">
        <v-btn @click="$emit('remove-todo', todo.id)">Del</v-btn>
      </div>
    </span>
  </li>
</template>


<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true
    }
  },
  name: "TodoItem"
};
</script>


<style scoped>
li {
  /* margin-left: auto;
  margin-right: auto;
  width: 500px;
  border: 2px solid #cccccc;
  border-radius: 12px;
  display: flex;
  padding: 0.5rem 1rem;
  margin-bottom: 1rem; */

  width: 500px;
  border: 2px solid #ccc;
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 2rem;
  margin-bottom: 1rem;
  margin-left: auto;
  margin-right: auto;

  /* border: 2px solid #cccccc;
  width: 500px;
  margin: auto auto;
  border-radius: 12px;
  list-style: none;
  margin-bottom: 10px; */
}

input {
  margin-right: 1rem;
}

.done {
  border-color: chartreuse;
}

.checkbox {
  padding-left: 10px;
  height: 20px;
  align-items: center;
}
</style>












