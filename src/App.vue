<template>
  <div>
    <h1>Witaj w systemie zapisów na zajęcia</h1>
    <span v-if="state === 0">Zaloguj się e-mailem </span>
    <input v-if="state === 0" type="email" v-model="email" />
    <button v-if="state === 0" @click="changeState(1)">Wchodzę</button>

    <h2 v-if="state === 1">Witaj {{ email }}!</h2>
    <a v-if="state === 1" @click="changeState(0)">Wyloguj</a>
  </div>
</template>

<script>
import "milligram";
export default {
  data() {
    return {
      email: "",
      password: "",
      state: 0,
    };
  },
  methods: {
    changeState(state) {
      if (state === 0) {
        this.email = "";
      }
      this.state = state;
    },
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
