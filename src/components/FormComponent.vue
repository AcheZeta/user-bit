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
          body: this.postBody,
          title: this.postTitle
        })
        .then(() => {
          this.posts.push({
            title: this.postTitle,
            body: this.postBody
          });
        });
    }
  }
};
</script>
