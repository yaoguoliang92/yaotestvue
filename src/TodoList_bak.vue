<template>
  <div>
    <div>
      <input type="text" v-model="inputvalue">
      <button @click="handlesubmit">按钮</button>
    </div>
    <ul>
      <todo-item
        v-for="(item,index) of list"
        :index='index'
        :key="index"
        :content='item'
        @delete='handlerdelete'
      ></todo-item>
    </ul>
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
    handlesubmit: function () {
      this.list.push(this.inputvalue)
      this.inputvalue = ''
    },
    handlerdelete: function (index) {
      this.list.splice(index, 1)
    }
  }
}
</script>

<style>

</style>
