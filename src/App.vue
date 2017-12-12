<template>
  <div id="app">
    <header>
      <span>Vue.js PWA</span>
    </header>
    <main>
      <progress-bar/>
      <ul>
        <todo-item description="Test" color="blue" v-on:select="itemWasSelected" :selected="todoItems[0].selected"></todo-item>
        <todo-item description="Test"></todo-item>
        <todo-item description="Test"></todo-item>
      </ul>
    </main>
  </div>
</template>

<script>
import Hello from './components/Hello'
import TodoItem from './components/TodoItem'
import ProgressBar from './components/ProgressBar'

export default {
  name: 'app',
  components: {
    Hello,
    TodoItem,
    ProgressBar
  },
  data: function () {
    return {
      todoItems: [
        {
          description: 'sdfsdf',
          selected: false
        }
      ]
    }
  },
  methods: {
    itemWasSelected: function () {
      this.$data.todoItems[0].selected = !this.$data.todoItems[0].selected
    }
  }
}
</script>

<style>
body {
  margin: 0;
  background: black;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

main {
  text-align: center;
  margin-top: 40px;
}

header {
  margin: 0;
  height: 56px;
  padding: 0 16px 0 24px;
  background-color: #35495E;
  color: #ffffff;
}

header span {
  display: block;
  position: relative;
  font-size: 20px;
  line-height: 1;
  letter-spacing: .02em;
  font-weight: 400;
  box-sizing: border-box;
  padding-top: 16px;
}
</style>
