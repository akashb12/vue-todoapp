<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <alert mode="danger">firsst</alert>
     <alert mode="primary">second</alert>
     <div>
     <input type="text" v-model="lastname" placeholder="Enter Name">
     <p>{{lastname}}</p>
     </div>
     <button @click="clickme">click me</button>
     <input type="text" @keyup.enter="dosomething" placeholder="Enter Code">
     <h3>loops</h3>
     <ul>
     <li v-for ="person in students"
     v-bind:key="person">{{person}}</li>
</ul>  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data(){
    return{
      lastname:"bhat",
      students:["akash","nidhi"]
    }
  },
    methods:{
      clickme(){
        console.log("You clicked on button")
      },

    dosomething(){
      console.log("done")
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
