<template>
  <div >
    {{msg}}
  </div>
</template>

<script>
export default {
  //组件标签中，只能使用函数或者对象
  data(){
    return {
      msg:"helleow"
    }
  }
}

</script>

<style >
  .msg{
    color: red;
    font-size: 24px;
  }
</style>
