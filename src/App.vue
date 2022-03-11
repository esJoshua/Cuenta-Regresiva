<template>
  <div id="app">
    <div>
      <h1>Cuenta Regresiva</h1>
      <h2>{{ countdown }} segundos</h2>
      <div class="">
        <button class="btn btn-primary mx-2" @click="iniciar(3)">3 seg</button>
        <button class="btn btn-danger mx-2" @click="iniciar(10)">10 seg</button>
      </div>
      <img alt="Vue logo" src="./assets/logo.png" />
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
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h2 {
  color: gray;
}
</style>
