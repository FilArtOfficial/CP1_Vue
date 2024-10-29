<template>
  <div>
    <AddTodo :addNewTodo="addNewTodo" />
    <TodoList
      :todos="todos"
      :removeTodo="removeTodo"
      :changeTodo="changeTodo"
    />
  </div>
</template>

<script>
import AddTodo from './components/AddTodo.vue';
import TodoList from './components/TodoList.vue';

export default {
  components: {
    AddTodo,
    TodoList,
  },
  data() {
    return {
      todos: [
        { id: 1, title: 'Позавтракать', completed: true },
        { id: 2, title: 'Почистить огурцы', completed: false },
        { id: 3, title: 'Помыть кота', completed: true },
      ],
    };
  },
  methods: {
    addNewTodo(title) {
      this.todos.push({
        id: Date.now(),
        title,
        completed: false,
      });
    },
    removeTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    changeTodo(id) {
      this.todos = this.todos.map(todo =>
        todo.id === id ? { ...todo, completed: !todo.completed } : todo
      );
    },
  },
};
</script>
