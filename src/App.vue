
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
        { 
          id: 1,
          text: "Very cute dog. 10/10."
        },
        { 
          id: 2,
          text: "Cute Pupper :)"
        }
      ]
    }
  },
  methods: {
    newComment(text) {
      const lastId = this.comments.map(c => c).pop().id
      if (this.comments.length < 5) {
        this.comments = [...this.comments, { id: lastId + 1, text } ]
      }
    },
    removeComment(commentId) {
      this.comments = this.comments.filter(c => c.id !== commentId)
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
