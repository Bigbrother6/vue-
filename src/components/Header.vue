<template>
  <header >
  	<h1>{{title2}}</h1>
    <h3>{{title}}</h3>
    <h3 v-on:click="changeTitle()">第3行</h3>
  </header>
</template>

<script>

export default {
  props:{title:{type:String}},
  data() {
    return {
      title2: "Vue Demo"
    }
  },

  methods: {
    changeTitle(){
      this.$emit("titleChanged","header子向父传值")
    },
 
  },

  // beforeCreate: function () {
  //   alert("组件实例化之前");
  //
  // },
  // created: function () {
  //   alert("组件实例化完成，但页面没显示");
  //   //请求接口  获取数据
  // },
  // beforeMount: function () {
  //   alert("组件实例化完成，但页面没显示，但虚拟dom已经配置");
  // },
  // mounted: function () {
  //  alert("组件挂载后，此方法执行后，页面显示");
 
  // },
  // beforeUpdate: function () {
  //   alert("组件更新前，页面仍未更新，但虚拟dom已经配置");
  // },
  // update: function () {
  //  alert("组件更新，此方法执行后，页面显示");
  //  //页面增删改查
  // },
  // beforeDestroy: function () {
  //   alert("组件销毁前");
  // },
  // destroyed: function () {
  //   alert("组件销毁")
  // },

}
</script>

<style scoped>
header{
	background: hotpink;
	padding: 10px;
}

h1{
	color: #eee;
	text-align: center;
}
</style>
