// ToDoItem.vue
<template>
  <div v-bind:class="{ 'completed' : todoItem.completed }">
        <p @click="markComplete">{{ todoItem.title }}</p>
        <button @click="$emit('delete-todo-event', todoItem.id)">Löschen</button>
  </div>
</template>

<script>
export default {
  name: 'ToDoItem',
  components: {
  },
  methods: {
    markComplete(){
      this.todoItem.completed = !this.todoItem.completed
    }
  },
  props: [
    "todoItem"
  ]
}
</script>
<style>
      .completed {
        text-decoration: line-through;
      }
</style>