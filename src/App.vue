<template>
  <div id="app">
    <Title />
		<div class="input-contain">
			<BaseInput class="base-input" />
			<AddBtn	class="add-btn"/>
		</div>
		<List />
  </div>
</template>

<script>
import Vue from 'vue'
import Title from './components/Title'
import BaseInput from './components/BaseInput'
import AddBtn from './components/AddBtn'
import List from './components/List'

Vue.prototype.$bus = new Vue()

export default {
  name: 'app',
  components: {
    Title,
		BaseInput,
		AddBtn,
		List
  },
	data(){
		return {
		}
	}
}
</script>

<style lang="scss">
*{margin: 0;padding: 0;box-sizing: border-box;}
#app {
	padding-top: 50px;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
	width: 500px;
	margin: 0 auto;
}
.input-contain{
	display: flex;
	align-items: center;
	justify-content: center;
	.add-btn{
		margin-left: 30px;
	}
}
</style>
