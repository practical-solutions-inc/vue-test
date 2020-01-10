<template>
  <div class="comments">
      <div v-bind:key="comment" v-for="comment in comments" class="comment">
        {{comment}}
        <span @click="remove(comment)" class="remove-button">Remove</span>
      </div>
  </div>
</template>

<script>
/* eslint-disable no-unused-vars */
/* eslint-disable no-console */

export default {
    name: 'Comments',
    props: {
        comments: Array
    },
    methods: {
        remove(comment) {
            this.$emit('remove-comment', comment)
        }
    }
}
</script>

<style scoped>

.comment {
    background-color: aliceblue;
    border-radius: 10px;
    padding: 1rem;
    margin: 10px;
    width: auto; 
}

.remove-button {
    float: right;
    font-size: .8rem;
    background-color: blue;
    color: aliceblue;
    padding: 3px;
    border-radius: 5px;
    cursor: pointer;
}

.remove-button:hover {
    background-color: black;
}

</style>