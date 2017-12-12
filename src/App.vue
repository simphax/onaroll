<template>
  <div id="app">
    <main>
      <progress-bar :todos="todos" :totalTime="totalTime" :currentTime="currentTime" :currentDo="currentDo"/>
      <ul>
        <transition name="fade">
          <todo-item description="Test" color="blue" v-on:select="itemWasSelected" :selected="todos[0].selected"></todo-item>
          <todo-item description="Test"></todo-item>
          <todo-item description="Test"></todo-item>
        </transition>
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
      todos: [
        {
          description: 'Try Vue',
          time: 1.3,
          color: '#54a35a',
          selected: false
        },
        {
          description: 'Publish PWA',
          time: 2.7,
          color: '#9e66cc',
          selected: false
        },
        {
          description: 'Code night',
          time: 1.3,
          color: '#c98a32',
          selected: false
        }
      ],
      totalTime: 8,
      currentTime: 2,
      currentDo: false
    }
  },
  methods: {
    itemWasSelected: function () {
      this.$data.todos[0].selected = !this.$data.todos[0].selected
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
