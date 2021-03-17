<template>
  <div id="app">

    <div class="sun_top">
      <sun_top />
    </div>
    <div class="sunbody">
      <!-- 组件之间数据传递 传递方法函数-->
      <sun_add :sun_add_com="sun_add_com"/>
      <!-- 组件之间数据传递 传递数组-->
      <sun_list :sun_commonts="sun_commonts" :sun_del_com="sun_del_com" />
    </div>
  </div>
</template>

<script>
// 1、引入组件 sun_add 组件别名
import sun_add from './components/sun_left.vue'
import sun_list from './components/sun_right.vue'
import sun_top from './components/sun_top.vue'
export default {
  // 这个data放在那个组件中,需要查看那些组件需要这些数据，放在他们的父级中,如果只有一个组件需要则只放在当前组件中
  data(){
    return {
      sun_commonts:[
        {
          name:"sun1",content:"发表内容1"
        },
        {
          name:"sun2",content:"发表内容2"
        },
        {
          name:"sun3",content:"发表内容3"
        },
      ]
    }
  },
  methods:{
    //添加评论
    //数据在那个组件，就把增删改方法添加到那个组件中
    sun_add_com(val){
      this.sun_commonts.unshift(val) //把信息添加到数组的前面
    },
    sun_del_com(index){
      this.sun_commonts.splice(index,1) 
    }
  },
  //映射组件
  components:{
    //2、映射组件标签 sun_hello 也可写成 sun_hello:sun_hello
    sun_add,
    sun_list,
    sun_top
  }
}
</script>

<style>
  .sunbody,.sun_top{
    width: 700px;
    margin: 0 auto;

  }
</style>
