<template>
  <div>
    <button @click="removeTodo">remove</button>
  </div>
</template>

<script>
export default {
  data(){
    return {
      
    }
  },
  methods:{
    removeTodo(){
      this.$emit('removeTodo')
    }
  }
}
</script>

<style lang="scss" scoped>
  button{
    background-color: #62bfed;
    border: none;
    color: #fff;
    font-size: 12px;
    padding: 4px;
    border-radius: 4px;
    cursor: pointer;
    opacity: .9;
    transition: all .3s;
    outline: none;
    &:hover{opacity: 1;}
  }
</style>