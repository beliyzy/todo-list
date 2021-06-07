<template>
  <li
      class="TodoItem"
      :class="{ isCompleted: todo.completed }"
  >
    {{ todo.text }}
    <div class="Delete">
      <span @click="$emit('delete')">Delete</span>
    </div>
    <div class="Toggle">
      <span @click="$emit('toggle')">Toggle Active</span>
    </div>
  </li>
</template>

<script>
export default {
  name: "TodoItem",
  props: {
    todo: Object
  }
}
</script>

<style scoped>
.TodoItem {
  margin-top: 20px;
  background-color: #fc5296;
  background-image: linear-gradient(315deg, #fc5296 0%, #f67062 74%);
  width: 20%;
  height: 100px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.TodoItem.isCompleted {
  background-color: #3bb78f;
  background-image: linear-gradient(315deg, #3bb78f 0%, #0bab64 74%);
}

.Delete {
  position: absolute;
  bottom: 12px;
  right: 12px;
}

.Toggle {
  position: absolute;
  bottom: 12px;
  left: 12px;
}
</style>