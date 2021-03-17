<!--右边内容-->
<template>
    <li>{{sm.name}} ---- {{sm.content}} <a href="javascript:void(0)" @click="sunDelete">删除</a></li>
</template>

<script>
export default {
  //声明接收属性：只声明属性名,该组件即可拥有该属性，模版可直接读取
  // props:['sm'], 
  props:{
    sm:Object,
    sun_del_com:Function,
    index:Number
  },
  //声明接收属性：声明属性名和类型,该组件即可拥有该属性，模版可直接读取
  // props:{
  //   sm:Object
  // }
  methods:{
    sunDelete(){
      const {index,sun_del_com} = this
      if(window.confirm('确定删除${sm.name}的评论吗？')){
        sun_del_com(index)
        //alert(sm.name)
      }
    }
  }

}
</script>

<style>
.sun_r{
	float: right;
}
</style>

