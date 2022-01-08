<template >
  <div id="app">
    <form>
    <div>
        <label for="task" >add your task</label>
        <br />
        <input placeholder="enter task" type="text" v-model="formValues.task"/>
         <button type="button" @click="onbuttClick($event)">click me here</button>
    </div>
   <!-- <h1>{{JSON.stringify(formValues,null,2)}}</h1> -->
  </form>
  <div v-bind:style="{fontSize:'12px',textAlign:'center',}">
    <h2 v-for="(t,index) in tasks" :key="t">{{index+1}}. {{t}}</h2>
  </div>
  </div>

</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data()
  {return{
    num:3,
    formValues:{
      task:""
    },
    tasks:[],
    style:{
      color:'red'
    }
  }
},
methods: {
  onbuttClick()
  {
    this.tasks.push(this.formValues.task);
    this.formValues.task="";
    console.log(this.tasks);
  }
}

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height:100vh;
  margin-top: 60px;
}
form{
  width:'100%';
  display: flex;
  justify-content: center;

}
label{
  text-transform: uppercase;
  font-size:'40px';
  text-align: center;
}
input{
  width:70vh;

}
button{
  display: block;
}
</style>
