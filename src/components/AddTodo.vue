<template>
  <div class="input_elem">
    <input @keydown.enter="handler" />
  </div>
</template>

<script>
export default {
  props: ['addNewTodo'],
  methods: {
    handler(event) {
      this.addNewTodo(event.target.value);
      event.target.value = '';
    },
  },
};
</script>

<style scoped>
.input_elem {
  display: flex;
  justify-content: center;
  margin: 20px 400px;
}

.input_elem > input {
  width: 100%;
  box-shadow: 5px 5px 5px black;
}
</style>
