<template>
  <div id="app">
        <ol>
            <li v-for="todo in todos" :key="todo.id">
              {{ todo.text }}
            </li>
        </ol>

        <input type="text" v-model="newTodo" @keyup.enter="addTodo">

        <button @click="addTodo">Tambahkan</button>

        <div v-if="todos.length >= 4">Hebat!</div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      newTodo: '',
      todos: []
    }
  },

  methods: {
    addTodo() {
      this.todos.push({ text: this.newTodo })
      this.newTodo = ''
    },
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: rgb(99, 99, 99)
}
</style>
