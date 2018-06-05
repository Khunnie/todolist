<template>
  <div id="Todolist">
   	<input class="item" type="text" name="" v-model="inputValue">
   	<button @click="handleSubmit" class="btn">提交</button>
   	<h3>留言区域</h3>
   	<ul>
   		<Todoitem v-for="(item,index) of list" :key="index" :content="item" :index="index" @delete="handleDelete"></Todoitem>
   	</ul>
  </div>
</template>

<script>

import Todoitem from './components/Todoitem.vue'
export default {
	//定义数据data之前是对象，现在是函数
	components:{
		'Todoitem':Todoitem
	},
	data(){
		return{
			inputValue:'',
			list:[]
		}
	},
	methods:{
		handleSubmit(){
			this.list.push(this.inputValue)
			this.inputValue =""
		},
		handleDelete(index){
			this.list.splice(index,1)
		}
	}
}
</script>

<style>
*{font-size: 16px;}
input{
	height: 28px;
}
.btn{
	background-color: #02a3fe;
	color: #fff;
	padding: 4px 10px;
	border: none;
	border-radius: 4px;
}
ul,li{padding: 0;}
</style>
