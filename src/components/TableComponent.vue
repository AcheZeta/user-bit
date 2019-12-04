<template>
  <div class="hello">
    <table>
      <tr>
        <th>id</th>
        <th>UserId</th>
        <th>Title</th>
        <th>Body</th>
      </tr>
      <tr v-for="item in posts" :key="item.id">
        <td>{{ item.id }}</td>
        <td>{{ item.userId }}</td>
        <td>{{ item.title }}</td>
        <td>{{ item.body }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
import axios from "axios";
import env from "../config/env";

export default {
  name: "TableComponent",
  data() {
    return {
      posts: [],
      postBody: null,
      postTitle: null
    };
  },
  created: async function() {
    let postsResponse = await axios.get(`${env.endpoint}/posts/`);
    this.posts = postsResponse.data;
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
