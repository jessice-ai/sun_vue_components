<!--左边内容-->
<template>
  <div class="sun_l">
  	<form  >
  		姓名:<input type="text" name="" v-model="name"><br><br>
  		内容:<textarea v-model="content"></textarea><br><br>
  		<input type="button" name="" value="提交" @click="sunadd">
  	</form>
  </div>
</template>

<script>
export default {
	props:{
		//传过来的函数名称 sun_add_com 
		sun_add_com:{ //指定了属性名,指定了属性类型,指定了必要性
			type:Function, //这里的Function首字母大写
			required:true
		}
	},
	data(){
		return {
			name:"",
			content:""
		}
	},
	methods:{
		sunadd(){
			//1、检查合法性
			const name = this.name.trim()
			const content = this.content.trim()
			if(!name || !content){
				alert('姓名或内容不能为空')
				return
			}
			//2、根据输入内容，分装成一个对象
			const sunData = {
				name,content
			}
			//3、更新数据_数组
			this.sun_add_com(sunData)
			//4、清空输入
			this.name = ""
			this.content = ""
		}
	}
}
</script>

<style>
.sun_l{
	float: left;

}
</style>
