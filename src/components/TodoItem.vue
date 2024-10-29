<template>
    <div
      class="todo_item"
      :style="{ backgroundColor: completed ? 'green' : 'red' }"
      @dblclick="removeTodo"
      @click="changeTodo"
    >
      <h1>{{ title }}</h1>
    </div>
  </template>
  
  <script>
  export default {
    props: ['title', 'completed', 'removeTodo', 'changeTodo'],
  };
  </script>
  
  <style scoped>
  .todo_item {
    display: flex;
    flex-direction: column;
    margin: 20px 170px;
    padding: 10px;
    outline: 2px solid black;
    box-shadow: 5px 5px 5px black;
  }
  </style>
  