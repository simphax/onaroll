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
  data () {
    return {
      todos: [
        {
          description: 'Try Vue',
          time: 1.3,
          color: '#54a35a'
        },
        {
          description: 'Publish PWA',
          time: 2.7,
          color: '#9e66cc'
        },
        {
          description: 'Code night',
          time: 1.3,
          color: '#c98a32'
        }
      ],
      totalTime: 8
    }
  },
  methods: {
    percentage (todo) {
      const percent = 100 * todo.time / this.$data.totalTime
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
