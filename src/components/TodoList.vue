<template>
    <div>
      <TodoItem
        v-for="todo in todos"
        :key="todo.id"
        :title="todo.title"
        :completed="todo.completed"
        :removeTodo="() => removeTodo(todo.id)"
        :changeTodo="() => changeTodo(todo.id)"
      />
    </div>
  </template>
  
  <script>
  import TodoItem from './TodoItem.vue';
  
  export default {
    components: { TodoItem },
    props: ['todos', 'removeTodo', 'changeTodo'],
  };
  </script>
  