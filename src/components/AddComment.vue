/* eslint-disable no-console */
<template>
    <div class="add">
        <form @submit="onSubmit">
            <input type="text" v-model="comment" placeholder="Add Comment...">
            <input type="submit" value="Submit ">
        </form>
    </div>
</template>

<script>
export default {
    name: "AddTodo",
    data() {
      return {
        comment: ''
      }
    },
    methods: {
        onSubmit(e) {
            e.preventDefault()
            this.$emit('add-comment', this.comment)
            // eslint-disable-next-line no-console
            console.log(this.comment)
        }
    }
}
</script>

<style scoped>
form {
  display: flex;
  margin: 10px;
}
input[type="text"] {
  flex: 10;
  padding: 1rem;
  color: black;
  border: 1px solid aliceblue;
  border-top-left-radius: 10px;
  border-bottom-left-radius: 10px;
  outline: 0;
}
input[type="submit"] {
  flex: 2;
  background: aliceblue;
  color: black;
  border: 1px aliceblue solid;
  border-top-right-radius: 10px;
  border-bottom-right-radius: 10px;
  cursor: pointer;
}
</style>