<template>
  <li @click='handlerdelete'>{{content}}</li>
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

</style>
