<template>
  <div v-for="(item, index) in listaTareas" :key="index">
    <div class="alert alert-secondary mt-3 text-start" role="alert">
       <div class="d-flex justify-content-between align-items-center">
            <div >{{ index + 1 }} : {{ item }}</div>
            <button 
                type="button" 
                class="btn btn-sm btn-danger" 
                @click="eliminar(index)"
            >
                Eliminar
            </button>
       </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "desplegar",
  props: {
    listaTareas: Array,
  },
  methods: {
      eliminar(indice) {
          this.$emit("eliminarTarea",indice)
      }
  }
  
};
</script>

<style>
</style>