<template>
  <div id="home">
    <app-header v-bind:title="title" v-on:titleChanged="updateTitle($event)"></app-header>
    <app-users v-bind:users="users"></app-users>
    <app-users v-bind:users="users"></app-users>
    <app-footer v-bind:title="title" v-on:titleChanged="updatefooter($event)"></app-footer>
  </div>
</template>

<script>
  import Header from './Header'
  import Footer from './Footer'
  import Users from './Users'
  export default {
    name: 'home',
    components:{
      "app-header":Header,
      "app-footer":Footer,
      "app-users":Users
    },
    data(){
      return{
        users:[],
        title:"我是string number父传子的"
      }
    },
    computed:{

    },
    created(){
        this.$http.get("http://jsonplaceholder.typicode.com/users").then((data)=>{
            this.users=data.body;

        })
    },
    methods:{
      updateTitle(aa){
        alert(aa)
        this.title=aa;

      },
      updatefooter(title){
        alert("footer");
        this.title=title;
      }

    }
  }
</script>

<style scoped>

</style>
