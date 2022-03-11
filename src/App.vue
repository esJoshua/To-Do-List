<template>
  <div class="container" id="app">
    <div class="row justify-content-center">
      <h1 class="col-12 display-2">Crea una nueva tarea</h1>
      <div class="d-flex col-12 justify-content-center">
        <h2 class="mx-2">Tarea</h2>
        <input
          type="text"
          v-model="inputValue"
          placeholder="Ingresa nueva tarea"
        />
        <button class="btn btn-secondary mx-2" type="button" @click="addTask">
          Crear
        </button>
      </div>
      <h3 class="col-12 mt-4">Lista</h3>
      <div class="d-block">
        <ul class="list-group d-inline-block text-start">
          <li v-for="(task, i) in arrayTask" :key="i">
            {{ i + 1 }}: {{ task }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      inputValue: "",
      arrayTask: [],
    };
  },
  methods: {
    addTask() {
      if (!this.inputValue) alert("Ingresa una tarea");
      else {
        this.arrayTask.push(this.inputValue);
        this.inputValue = "";
      }
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: gray;
  margin-top: 60px;
}
h2,
li {
  color: black;
}
</style>
