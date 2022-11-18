<template>
  <div id="app">
  <form @submit.prevent="submitForm">
    <div>
      <label for="name">Name:</label><br>
      <input id="name" type="text" v-model="name" required/>
    </div>
    <div>
      <label for="email">Email:</label><br>
      <input id="email" type="email" v-model="email" required/>
    </div>
    <div>
      <label for="caps">HOW DO I TURN OFF CAPS LOCK:</label><br>
      <textarea id="caps" v-model="caps" required></textarea>
    </div>
    <button :class="[name ? activeClass : '']" type="submit">Submit</button>
    <div>
      <h3>Response from server:</h3>
      <pre>{{ response }}</pre>
    </div>
  </form>
</div>
</template>

<script>
import axios from 'axios'
export default {
  name: "vue_examples",
  data() {
    return {
      name: '',
      email: '',
      caps: '',
      response: '',
      activeClass: 'active'
    }
  },
  methods: {
    submitForm() {
      axios.post('//jsonplaceholder.typicode.com/posts', {
        name: this.name,
        email: this.email,
        caps: this.caps
      }).then(response => {
        this.response = JSON.stringify(response, null, 2)
      }).catch(error => {
        this.response = 'Error: ' + error.response.status
      })
    }
  }
}
</script>

<style>

#app {
  display: flex;
  justify-content: center;
  font-family: 'Work Sans', sans-serif;
}

form {
  width: 300px;
  padding: 10px 40px  
}

form label {
    text-transform: uppercase;
    font-size: 13px;
    letter-spacing: 0.03em;
    font-weight: bold;
}

form input, textarea {
    border: 1px solid #ccc;
    color: #333;
    width: calc(100% - 30px);
  }

form input, textarea, button {
    border-radius: 4px;
    padding: 8px 15px;
    font-family: 'Work Sans', sans-serif;
    font-weight: 300;
  }

form div {
    margin: 20px 0;
  }

form label {
    text-transform: uppercase;
    font-size: 13px;
    letter-spacing: 0.03em;
    font-weight: bold;
  }

button {
  color: white;
  border: none;
  width: 100%;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  background: #ccc;
  cursor: pointer;
  box-shadow: 0px 2px 3px rgba(0, 0, 0, 0.3);
  transition: 0.25s all ease;
  
}
button :hover {
    transform: translateY(2px);
  }

  .active {
  background-color: purple;
}

pre-content {
  width: 300px;
}
</style>
