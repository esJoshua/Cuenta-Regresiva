<template>
  <div id="app" class="container">
    <div class="row">
      <h1>Cuenta Regresiva</h1>
      <h2>{{ countdown }} segundos</h2>
      <div class="">
        <button class="btn btn-primary mx-2" @click="iniciar(3)">3 seg</button>
        <button class="btn btn-danger mx-2" @click="iniciar(10)">10 seg</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      countdown: 0,
      myInterval: "",
    };
  },
  methods: {
    iniciar(time) {
      this.countdown = time;
      clearInterval(this.myInterval);
      this.myInterval = setInterval(() => {
        if (this.countdown > 0) this.countdown--;
        else clearInterval(this.myInterval);
      }, 1000);
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
  color: #2c3e50;
  margin-top: 60px;
  ul {
    li {
      color: blue;
    }
  }
}
h2 {
  color: gray;
}
</style>
