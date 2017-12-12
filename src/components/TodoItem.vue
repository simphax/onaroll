<template>
  <li v-on:click="selectMe" :class="selected ? 'selected' : ''">
    <span class="ruta" :style="{backgroundColor: color}"></span>
    <span class="text" :class="selected ? 'selected' : ''">{{ description }}</span>
  </li>
</template>

<script>
export default {
  name: 'hello',
  props: ['description', 'time', 'color', 'selected'],
  methods: {
    selectMe: function () {
      this.$emit('select')
    }
  }
}
</script>

<style scoped>
li {
    margin: 100px;
    list-style: none;
    display: flex;
    align-content: center;
}
.selected {
  background: white;
}
.ruta {
    display: inline-block;
    width: 3rem;
    height: 3rem;
    background-color: mistyrose;
    margin-right: 2rem;
}
.text {
    display: inline-block;
    color: white;
    font-size: 2rem;
    line-height: 3rem;
}
.text_selected {
  color: black;
}
</style>
