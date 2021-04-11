<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
        <span>Tarea: </span>
    <input v-model="nuevaTarea" placeholder="Ingresa una nueva tarea">
    <button @click="agregarTarea()" class="btn btn-primary">Añadir</button>
    <Lista :tareas="tareas" @indexTarea="indexT = $event" />
  </div>
</template>

<script>
import Lista from "./components/Lista.vue";

export default {
  name: "App",
  components: {
    Lista,
  },
    data() {
    return {
      nuevaTarea: "",
      tareas: [],
      indexT: ""
    }
  },
      methods: {
    agregarTarea() {
      if (!this.nuevaTarea) return alert('Ingresa una tarea');
      this.tareas.push({tarea: this.nuevaTarea})
      this.limpiar()
    },
    limpiar(){
      this.nuevaTarea = ""
    }
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

input{
  margin: 1rem;
}
</style>
