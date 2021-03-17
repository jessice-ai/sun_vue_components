<!--右边内容-->
<template>
    <li>{{sm.name}} ---- {{sm.content}}</li>
</template>

<script>
export default {
  //声明接收属性：只声明属性名,该组件即可拥有该属性，模版可直接读取
  props:['sm'], 

  //声明接收属性：声明属性名和类型,该组件即可拥有该属性，模版可直接读取
  // props:{
  //   sm:Object
  // }


}
</script>

<style>
.sun_r{
	float: right;
}
</style>

