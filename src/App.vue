<template>
  <div class="container w-50">
    <h2>Lista de Tareas</h2>
    <div class="d-flex justify-content-between">
      <input 
        type="text" 
        class="form-control w-75" 
        v-model='tarea'
        @keyup.enter='agregarTarea' 
      />
      <button
        type="button"
        class="btn btn-primary"
        @click="agregarTarea"
      >
        Agregar
      </button>

    </div>    
    <desplegar 
      :listaTareas = listaTareas 
      @eliminarTarea="eliminarTareaPadre"
    />
  
  </div>
</template>

<script>
  // import HelloWorld from './components/HelloWorld.vue'
  import desplegar from './components/desplegar.vue'

  export default {
    name: "App",

    data(){
      return {
        tarea:"",
        listaTareas: [],
      }
    },

    components: {
      // HelloWorld
      desplegar
    },
    
    methods:{
      agregarTarea(){
        if(this.tarea == ""){
          alert('* no ha ingresado ninguna tarea')
        }else{
        this.listaTareas.push(this.tarea)
        this.tarea=""
        }
      },
      eliminarTareaPadre(childValue){
        this.listaTareas.splice(childValue,1)
      }

    }
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
