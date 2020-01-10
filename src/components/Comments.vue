<template>
  <div class="comments">
      <div v-bind:key="comment" v-for="comment in comments" class="comment">
          {{comment}}
      </div>
  </div>
</template>

<script>
export default {
    name: 'Comments',
    props: {
        comments: Array
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

</style>