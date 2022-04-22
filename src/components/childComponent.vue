<template>
  <div>
   
    <ul class="list-group" v-for="(tarea, id) in tareas" :key="tarea">
        <li class="list-group-item">{{ id + 1 }} - {{ tarea.nombre }} <b-button pill variant="danger" @click="deleteItem(index)">
          Eliminar</b-button>
          </li>
  </ul>
  </div>
 
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    tareas: Array
  },
 methods:{
   deleteItem(index){
     this.$emit("deleteItem", index)
   }
 }
}
</script>

<style>
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