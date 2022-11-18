<template>
  <div id="app">
    <input v-model="checkedNames" type="checkbox" id="john" value="John" />
    <label for="john"> John</label>

    <input v-model="checkedNames" type="checkbox" id="paul" value="Paul" />
    <label for="paul"> Paul</label>

    <input v-model="checkedNames" type="checkbox" id="george" value="George" />
    <label for="george"> George</label>

    <input v-model="checkedNames" type="checkbox" id="ringo" value="Ringo" />
    <label for="ringo"> Ringo</label>
    <br>
    <br>
    Checked names:<span>{{ checkedNames }}</span>
  </div>
</template>

<script>
export default {
  name: "vue_examples",
  data() {
    return {
      checkedNames: []
    };
  },
};
</script>

<style>
body {
  font-family: 'Bitter', serif;
}

#app {
  text-align: center;
  padding: 70px;
  font-size: 16px;
  margin: 0 auto;
  display: table;
  line-height: 2em;
}

label {
  padding-right: 10px;
}

span {
            color: green;
            font-weight: bold;
            font-size: 26px;
        }
</style>
