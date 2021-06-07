<template>
  <div id="app">
    <Title>Hello, I'm TODOLIST</Title>
    <TodoList
        :todos="todos"
        @delete-task="deleteTask"
        @toggle="toggle"
    />
    <div class="form">
      <Input label="Enter ur Text" :value="form.text" @input="inputText"/>
      <Checkbox label="Is Completed?" :value="form.completed" @input="inputChechbox"/>
      <div v-if="error" style="color: red">Enter smth</div>
      <Button @click="addTask">Add Task</Button>
    </div>
  </div>
</template>

<script>


import Title from "@/components/Title";
import TodoList from "@/components/TodoList";
import Input from "@/components/Input";
import Checkbox from "@/components/Checkbox";
import Button from "@/components/Button";

export default {
  name: 'App',
  components: {
    Button,
    Checkbox,
    Input,
    TodoList,
    Title
  },
  data: () => ({
    todos: [
      {
        id: 1,
        text: 'First task',
        completed: false,
      },
      {
        id: 2,
        text: 'Second task',
        completed: true,
      },
      {
        id: 3,
        text: 'Third task',
        completed: false,
      }
    ],
    form: {
      text: '',
      completed: '',
    }
  }),
  methods: {
    inputText(value) {
      this.form.text = value;
    },
    inputChechbox(value) {
      this.form.completed = value;
    },
    addTask() {
      if (this.form.text !== '') {
        this.todos.push({
          id: Date.now(),
          text: this.form.text,
          completed: this.form.completed,
        });
      }
      this.form.text = '';
      this.form.completed = false;
    },
    deleteTask(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    toggle(id) {
      const item = this.todos.find(todo => todo.id === id);
      item.completed = !item.completed;
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #b3cdd1;
  background-image: linear-gradient(315deg, #b3cdd1 0%, #9fa4c4 74%);
  height: 400vh;
}

.form {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
