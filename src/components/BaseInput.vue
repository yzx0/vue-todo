<template>
    <input type="text" @input="onInput" :value="value" placeholder="请输入todo..." />
</template>
<script>
/**
 * 清空input
 * value = ''
 * 只有触发input 才会改变text,
 * v-model="value" === :value="value" @input= "value = $event.target.value"
 */
export default {
  data() {
    return {
      value:''
    };
  },
  mounted() {
    this.$bus.$on("addTodo", () => {
      this.value = ''
    });
  },
  methods: {
    onInput(e) {
      this.$bus.$emit("input", e.target.value);
      this.value = e.target.value
    }
  }
};
</script>

<style lang="scss" scoped>
input {
  flex-grow: 1;
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 10px;
  background-color: #fff;
  transition: all 0.3s;
  &:focus {
    border-color: #999;
    outline: none;
  }
}
</style>