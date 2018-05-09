<template>
<div>
  <div>
    <input type="text" v-model="inputvalue">
    <button @click="handlersubmit">按钮</button>
  </div>
  <div>
    <todo-item
    v-for="(item,index) of list"
    :key='index'
    :index='index'
    :content='item'
    @delete='handlerdel'
    ></todo-item>
  </div>
</div>
</template>

<script>
import TodoItem from './components/TodoItem'

export default {
  components: {
    'todo-item': TodoItem
  },
  data () {
    return {
      inputvalue: 123,
      list: []
    }
  },
  methods: {
    handlersubmit: function () {
      this.list.push(this.inputvalue)
      this.inputvalue = ''
    },
    handlerdel: function (index) {
      this.list.splice(index, 1)
    }

  }
}
</script>

<style>

</style>
