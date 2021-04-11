<template>
  <div>
    <ul>
      <li v-for="tarea, i in tareas" :key="i">Tarea N°{{i + 1}}: {{tarea.tarea}} <button @click="eliminar(tarea)" class="btn btn-danger">Eliminar</button></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Lista",
  props: {
    tareas: Array,
    default: () => []
  },

  methods: {
    eliminar(tarea) {
      let index = this.tareas.indexOf(tarea)
      this.tareas.splice(index, 1)
      this.$emit('indexTarea', index)
    }
  },
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

li{
  margin-top: 1rem;
}
a {
  color: #42b983;
}
</style>
