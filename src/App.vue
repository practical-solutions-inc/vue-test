<template>
  <div id="app">
    <img class="pug-picture" alt="PUG" src="./assets/pug.jpg">
    <Comments :comments="comments"/>
  </div>
</template>

<script>
import Comments from './components/Comments.vue'

export default {
  name: 'app',
  components: {
    Comments
  },
  data() {
    return {
      comments: [
        "Omg that's the cUTEST DOG EVER",
        "14/10. Very good boi.",
        "My Dog is better :/"
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
}

.pug-picture {
  max-width: 800px;
  display: block;
  margin-left: auto;
  margin-right: auto;
}
</style>
