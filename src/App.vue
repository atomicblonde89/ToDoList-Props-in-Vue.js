<template>
  <div id="app">
    <div class="container">
      <form v-on:submit.prevent="ingresarTarea">
        <p>Tarea: <input type="text" v-model="nombre" placeholder="Ingresa nueva tarea"/></p>
        <b-button pill variant="outline-dark" type="submit" >Añadir</b-button>
      </form>
      <br>
        <h2>Lista de Tareas: </h2>
       <childComponent :tareas="this.tareas" @deleteItem="deleteItem" />
     
    </div> 
  
  </div>
 
</template>

<script>
import childComponent from "./components/childComponent.vue"
export default {
  name: "App",
  components: {
    childComponent,
  },
  data() {
    return {
      nombre: "",
      tareas: [],
    };
  },
  methods: {
    ingresarTarea: function () {
      this.tareas.push({
        nombre: this.nombre,
      });
      this.nombre = "";
    },
    deleteItem: function(index){
        this.tareas.splice(index,1)
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  
}
</style>

