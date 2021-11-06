// ToDos.vue
<template>
    <div>
        <h1>Meine To-Do-Liste</h1>
        <ul>
        <li v-bind:key="item.id" v-for ="item in todoEntries">
            <ToDoItem v-bind:todoItem="item">
        </li>
        </ul>
        <ToDoItem v-bind:todoItem="item" @delete-todo-event="$emit('delete-todo-event', item.id)"/>
        <ToDos v-bind:todoEntries="todoEntries" @delete-todo-event="deleteToDoItem"/>
    </div>
</template>
<script>
import ToDoItem from "./ToDoItem";

export default {
  name: 'ToDos',
  components: {
      ToDoItem
  },
  props: [
      "todoEntries"
  ]
}
</script>