<template>
  <div>
    <div>
      <input type="text" v-model="postTitle" />
      <input type="text" v-model="postBody" @change="postPost()" />
    </div>
    <ul v-if="posts && posts.length">
      <li v-for="post in posts" :key="post.errors">
        <p>
          <strong>{{ post.title }}</strong>
        </p>
        <p>{{ post.body }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      posts: [],
      errors: [],
      postBody: "",
      postTitle: ""
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
  },
  // Fetches posts when the component is created.
  created() {
    axios
      .get(`http://jsonplaceholder.typicode.com/posts`)
      .then(response => {
        // JSON responses are automatically parsed.
        this.posts = response.data;
      })
      .catch(e => {
        this.errors.push(e);
      });
  }
};
</script>
