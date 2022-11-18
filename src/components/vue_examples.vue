<template>
 <div id="app">
  <h3>What is your favorite kind of taco?</h3>
  <p v-text="tacos"></p>
  <p>{{ tacos }}</p>
  <p><input v-model="tacos" /></p>
</div>
</template>

<script>
export default {
  name: "vue_examples",
  data() {
    return {
      tacos: 'I like Al Pastor tacos'      }
  }
}
</script>

<style>
body {
  font-family: 'Bitter', serif;
}

#app {
  text-align: center;
  padding: 70px;
  max-width: 360px;
  font-size: 16px;
  margin: 0 auto;
  display: table;
  line-height: 2em;
}

label {
  padding-right: 10px;
}

button {
  border: none;
  background: orangered;
  color: white;
  padding: 0.5em 1em;
  border-radius: 3px;
}
</style>
