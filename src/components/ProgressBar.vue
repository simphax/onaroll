<template>
  <div class="progress-bar">
    <div class="progress-bar-todo"
         v-for="todo in todos"
         :style="{backgroundColor: todo.color, width: percentage(todo)}">
    </div>
  </div>
</template>

<script>
export default {
  name: 'progress-bar',
  props: ['todos', 'totalTime'],
  methods: {
    percentage (todo) {
      const percent = 100 * todo.time / this.$props.totalTime
      return `${percent}%`
    }
  }
}
</script>

<style>
  .progress-bar {
    background-color: #ccc;
    display: flex;
    flex-direction: row;
  }

  .progress-bar-todo {
    box-sizing: border-box;
    color: #fff;
    height: 50px;
    text-align: center;
    position: relative;
  }

  .progress-bar-todo:last-child:after {
    background-color: #666;
    content: "";
    height: 130%;
    position: absolute;
    right: -4px;
    top: -15%;
    width: 8px;
  }
</style>
