<template>
  <ul class="TodoList">
    <TodoItem
        v-for="todo in todos"
        :key="todo.id"
        :todo="todo"
        @delete="$emit('delete-task', todo.id)"
        @toggle="$emit('toggle', todo.id)"
    />
  </ul>
</template>

<script>
import TodoItem from "@/components/TodoItem";

export default {
  name: "TodoList",
  components: {TodoItem},
  props: {
    todos: Array
  },
}
</script>

<style scoped>
.TodoList {
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  list-style: none;
}
</style>