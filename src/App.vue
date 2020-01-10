<template>
  <div id="app">
    <img class="pug-picture" alt="PUG" src="./assets/pug.jpg">
    <Comments :comments="comments"/>
    <AddComment v-on:add-comment="newComment" />
  </div>
</template>

<script>
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
      // eslint-disable-next-line no-console
      this.comments = [...this.comments, comment ]
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
  max-width: 800px;
  display: block;
  margin-left: auto;
  margin-right: auto;
}
</style>
