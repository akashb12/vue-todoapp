<template>
  <div class="todos">
    <h1>todoapp</h1>
    <input type="text" v-model="title" placeholder="What You want to do?">
    <button @click="add">Add to list</button>
     <ul>
     <li v-for ="(todo,index) in todos"
     v-bind:key="todo">{{todo}}<span class="remove" @click="remove(index)">x</span></li>
</ul> 
     </div>
</template>

<script>
export default {
  name: "todo",
  props: {
    msg: String
  },
  data(){
      return{
          title:"",
          todos:[
              "go to shop"
          ]
      }
  },
  methods:{
      add(){
          this.todos.push(this.title)

      },
      remove(id){
       // console.log(id);
        //this.todos.splice(id,1);
        //this is using vuejs
        this.$delete(this.todos,id);

      }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
ul li{
  padding: 0.4rem;

}
.remove{
  padding:.3rem .6rem;
  background-color: red;
  border-radius: 30px;
  color: white;
}
</style>
