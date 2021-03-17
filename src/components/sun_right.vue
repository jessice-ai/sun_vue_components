<!--右边内容-->
<template>
  <div class="sun_r">
  	<ul>
  		<!-- 组件之间数据传递 :sm="sm" 作用是吧值传递给sun_item.vue组件 -->
  		<sun_item v-for="(sm,index) in sun_commonts" :key="index" :sm="sm"/>
  	</ul>
  </div>
</template>

<script>
	import sun_item from './sun_item.vue'
export default {
	//声明接收属性：只声明属性名,该组件即可拥有该属性，模版可直接读取
	props:['sun_commonts'],

	//组件映射
	components:{
		sun_item
	}
}
</script>

<style>
.sun_r{
	float: right;
}
</style>

