
<template>
  <div id="app">
    <img class="pug-picture" alt="PUG" src="./assets/pug.jpg">
    <Comments v-on:remove-comment="removeComment" :comments="comments"/>
    <AddComment v-on:add-comment="newComment" />
  </div>
</template>

<script>
/* eslint-disable no-unused-vars */
/* eslint-disable no-console */

import Comments from './components/Comments.vue'
import AddComment from './components/AddComment.vue'

export default {
  name: 'app',
  components: {
    Comments,
    AddComment
  },
  data() {
    return {
      comments: [
        "Very cute dog. 10/10.",
        "Pretty Pupper"
      ]
    }
  },
  methods: {
    newComment(comment) {
      this.comments = [...this.comments, comment ]
    },
    removeComment(comment) {
      // oh no it's empty!!! whatever will you do???
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  padding: 1rem 20vw;
}

.pug-picture {
  width: 100%;
  max-width: 500px;
  display: block;
  margin-left: auto;
  margin-right: auto;
}
</style>
