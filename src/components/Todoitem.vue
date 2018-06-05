<template>
  <li class="item">{{content}}<a href="javascript:;" @click="handleClick">删除</a></li>
    
</template>

<script>
export default {
  props:['content','index'],
  methods:{
    handleClick(){
      this.$emit('delete',this.index)
    }
  }
}
</script>
<!--scoped样式只对自己这个组件有效果 -->
<style scoped>
.item{
  list-style: none;
  color: #333;
}
a{
  padding-left: 10px;
  text-decoration: none;
}
</style>
