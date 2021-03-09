<template>
  <form @submit.prevent="procesarFormulario">
    <Inputs :tarea="tarea" />
  </form>
    <ListaTareas />
</template>

<script>

import Inputs from '../components/Inputs';
import ListaTareas from '../components/ListaTareas';
import {mapActions} from 'vuex';
const shortid = require('shortid')

export default {
  name: 'Home',
  components: {
    Inputs,
    ListaTareas
  },
  data() {
    return {
      tarea: {
        id: '',
        nombre: '',
        categorias: [],
        estado: '',
        numero: 0
      }
    }
  },
  methods: {
    ...mapActions(['setTareas']),
    procesarFormulario() {
      console.log(this.tarea);
      if(this.tarea.nombre.trim() === ""){
        console.log('Campo Vacío')
        return
      } 

      console.log('No está vacío');      

      //Generar ID
      this.tarea.id = shortid.generate();

      //Enviar los datos
      this.setTareas(this.tarea)

      //Limpiar datos
      this.tarea = {
        id: '',
        nombre : '',
        categorias : [],
        estado: '',
        numero : 0
      }
    }
  }
}
</script>
