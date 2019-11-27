<template>
  <div>
    <ul key="1">
      <li v-for="(item,index) in todos" :key="index">
        <div class="left">
          <span class="index">{{index+1}}.</span>
          <span>{{item}}</span>
        </div>
        <RemoveBtn @removeTodo="removeTodo(index)" class="rm-btn"/>
      </li>
    </ul>
  </div>
</template>

<script>
import RemoveBtn from './RemoveBtn'
export default {
  name:'list',
  components:{
    RemoveBtn
  },
  data(){
    return {
      todos:[]
    }
  },
  created(){
    this.$bus.$on('addTodo',value => {
      value ? this.todos.push(value) : alert('请输入todo')
    })
  },
  methods:{
    removeTodo(index){
      this.todos.splice(index,1)
    }
  }
}
</script>

<style lang="scss" scoped>
  ul{
    font-size: 16px;
    li{
      display: flex;
      align-items: flex-end;
      justify-content: space-between;
      padding-top: 10px;
      padding-bottom: 10px;
      border-bottom: 1px solid #eee;
    }
  }
  .rm-btn{
    margin-left: 10px;
  }
  .index{
    margin-right: 6px;
  }
</style>