<template>
  <div id="app">
    <div class="container is-fluid">
      <div class="columns is-centered is-multiline">
        <div class="column is-one-third has-background-black-ter has-text-white">
          <h1 class="title is-bold has-text-white">HELL LET LOOSE ARTILLERY CALCULATOR</h1>
          <hr>
          <label class="label has-text-white">Meters</label>
          <input class="input" v-model="inputData" @input="getDistance">
        </div>
      </div>

      <div class="columns is-centered">
        <div class="column is-one-third has-background-grey-light">
          <span class="is-bold title">{{ result }} MIL</span>
        </div>
      </div>
      <div class="columns is-centered">
        <div class="column is-narrow p-0 pt-2">
          <div class="buttons has-text-centered">
        <button class="button is-success is-fullwidth" @click="getDistance">Calculate</button>
        <button class="button is-danger is-fullwidth" @click="getDistance">Clear</button>
      </div>
        </div>
      </div>
    </div>
    <br><br>
    <div class="columns is-centered">
      <div class="column is-one-third">
        The used formula is:<br><br> <span class="is-bold subtitle">978 - (n / 100 - 1) * 24</span>
      </div>
    </div>
  </div>

</template>

<script>


export default {
  name: 'App',
  components: {

  },
  data: function () {
    return {
      inputData: null,
      result: "",
    }
  },
  methods: {
    getDistance() {
      this.result = this.calculateDistance(this.inputData);
    },

    calculateDistance(n) {
      if (isNaN(n)) return 0;
      return (978 - (n / 100 - 1) * 24).toFixed(2)
    }
  }
}
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
