<template>
  <footer v-on:click="chan()">
  	<h1>{{title3}}{{title}}</h1>
  </footer>
</template>

<script>

export default {
  props:{title:{type:String}},
  data(){
    return{
      title3:"Copyright 2017 Vue.js"
    }
  },
  methods:{
    chan(){
      this.$emit("titleChanged","footer子向父传值")
    }
  }
}
</script>

<style scoped>
footer{
	background: #eee;
	padding: 6px;
}

h1{
	color: lightgreen;
	text-align: center;
}
</style>
