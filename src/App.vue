<template>
  <div id="app">
    <div class="container">
      <div class="col-md-6 offset-md-3">
        <h1 class="text-center">Todo-List</h1>
        <input type="text" class="form-control md-4" v-model="userInput" @keyup.enter="addNewTodo">

        <div class="list-group">
          <button class="list-group-item text-left" v-for="todo in todoList" v-bind:key="todo">
            {{ todo }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      userInput: '',
      todoList: []
    };
  },
  methods: {
    addNewTodo() {
      this.todoList.push(this.userInput);
      this.userInput = '';
    }
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
