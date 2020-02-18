<template>
  <v-container v-bind:class="{done: todo.completed}">
    <!-- <li v-bind:class="{done: todo.completed}">
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
         <v-btn color="error" @click="$emit('remove-todo', todo.id)">Del</v-btn>
       </div>
     </span>
    </li>-->

    <v-card class="mx-auto" max-width="344" outlined :elevation="8">
      <v-list-item three-line>
        <v-list-item-content>
          <v-list-item-title class="headline mb-1">{{todo.title}}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-card-actions>
        <v-btn color="green" text @change="todo.completed = !todo.completed">Done</v-btn>
        <v-btn color="error" text @click="$emit('remove-todo', todo.id)">Delete</v-btn>
      </v-card-actions>
    </v-card>
  </v-container>
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
.v-container {
  width: 500px;
}

input {
  margin-right: 1rem;
}

.done {
  border: 2px solid;
  border-color: chartreuse;
}

.checkbox {
  padding-right: 500px;
  height: 20px;
  align-items: center;
}
</style>












