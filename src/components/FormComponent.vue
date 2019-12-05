<template>
  <input type="text" v-model="postBody" @change="postPost()" />
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      postBody: "",
      errors: [],
      posts: ""
    };
  },
  methods: {
    // Pushes posts to the server when called.
    postPost() {
      axios
        .post(`http://jsonplaceholder.typicode.com/posts`, {
          body: this.postBody
        })
        .then(response => {
          this.posts = response.data;
        })
        .catch(e => {
          this.errors.push(e);
        });
    }
  }
};
</script>
