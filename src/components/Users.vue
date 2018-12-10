<template>
  <div id="users">
  	<ul>
  		<li v-on:click="user.show = !user.show" v-for="user in users">
  			<h2>{{user.name}}</h2>
  			<h3>{{user.email}}</h3>
  		</li>
  	</ul>
    <button v-on:click="del()">del</button>
  </div>
</template>
  <!--传值： string number boolean-->
<script>

export default {
  name:'users',
 // props:["users"],
 //属性传直
  props:{          //接受父传过来的
    users:{type:Array,required:true}
  },
  data(){
    return{

    }
  },
  methods:{
     del(){
       this.users.pop();
     }
  }
}
</script>

<style scoped>
#users{
	width: 100%;
	max-width: 1200px;
	margin: 40px auto;
	padding: 0 20px;
	box-sizing: border-box;
}

ul{
	display: flex;
	flex-wrap: wrap;
	list-style-type: none;
	padding: 0;
}

li{
	flex-grow: 1;
	flex-basis: 300px;
	text-align: center;
	padding: 30px;
	border: 1px solid #222;
	margin: 10px;
}
</style>
