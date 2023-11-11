<template>
  <div>
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: {
      type: String,
      default: 'Not HelloWorld'
    }
  },
}
</script>

<style lang="scss" scoped>

</style>