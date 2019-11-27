<template>
  <button @click="addItem">add</button>
</template>
<script>

export default {
  created(){
    this.$bus.$on('input',value=>{
      this.text = value
    })
  },
  data(){
    return {
      text:''
    }
  },
  methods:{
    addItem() {
      this.$bus.$emit("addTodo", this.text);
      this.text = ''
    }
  }
}
</script>

<style lang="scss" scoped>
button {
  background-color: #62bfed;
  border: none;
  color: #fff;
  font-size: 16px;
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
  opacity: 0.9;
  transition: all 0.3s;
  outline: none;
  &:hover {
    opacity: 1;
  }
}
</style>