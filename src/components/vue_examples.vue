<template>
  <div id="app">
    <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/vue-post-photo.jpg" class="main-photo">
    <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/vue-main-profile.jpg" class="main-profile">
    <div class="main-info">
      <span class="name">Julianne Delfina</span>
      <h3>"It's lovely after it rains"</h3>
    </div>
    <hr>
    
    <ul>
      <li v-for="comment in comments" :key="comment">
        {{ comment }}
      </li>
    </ul>

    <input @keyup.enter="addComment" v-model="newComment" placeholder="Add a comment" />
  </div>
</template>

<script>
export default {
  name: "vue_examples",
  data() {
    return {
      newComment: '',
      comments: [
        'Looks great Julianne!',
        'I love the sea',
        'Where are you at?'
      ]
    }
  },
  methods: {
    addComment() {
      this.comments.push(this.newComment)
      this.newComment = ''
    }
  }
}
</script>

<style>
body {
  font-family: 'Playfair Display', serif;
}

#app {
  background: #212222;
  color: #fff;
  letter-spacing: 0.04em;
  text-align: center;
  margin: 60px;
  width: 370px;
  margin: 0 auto;
  display: table;
  padding: 20px;
  line-height: 1.4em;
}

.name {
  color: #ccc;
}

small {
  color: #bbb;
  font-size: 10px;
}

h3 {
  margin: 5px 0 4px;
}

.main-photo {
  width: 300px;
}

.main-profile {
  float: left;
  border: 3px solid white;
  margin: -25px 0 0 20px;
  position: relative;
  width: 80px;
}

.main-info {
  float: left;
  padding: 10px 20px;
  text-align: left;
  margin-bottom: 15px;

}

.main-info after {
  content: "";
  display: table;
  clear: both;
}

li {
  list-style: none outside none;
  text-align: left;
  padding: 10px 0;
  border-bottom: 1px solid #555;
}

ul {
  margin: 0;
  padding: 0 35px;
}

hr {
  margin: 75px 0 0 32px;
  width: 300px;
  border-top: 0;
  border-bottom: 1px solid #555;
}

input {
  font-family: 'Playfair Display', serif;
  width: 280px;
  margin: 30px 0;
  padding: 8px 10px;
  outline: 0;
}
</style>
