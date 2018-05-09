<template>
  <li class="item" @click='handlerdelete'>{{content}}</li>
</template>

<script>
export default {
  props: ['content', 'index'],
  methods: {
    handlerdelete: function () {
      this.$emit('delete', this.index)
    }
  }
}
</script>

<style scoped>
/* scope作用域  当前组件,不加则全局生效 */
.item{
  color:#f0f0f0;
}
</style>
