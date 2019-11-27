<template>
    <h3>{{title}}</h3>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      default: "欢迎使用todo"
    }
  }
};
</script>

<style lang="scss" scoped>
  h3{
    margin-top: 20px;
    margin-bottom: 20px;
  }
</style>