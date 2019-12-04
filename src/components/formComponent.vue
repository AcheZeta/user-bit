<template>
  <div>
    <input type="text" v-model="postTitle" placeholder="title" />
    <input type="text" v-model="postBody" placeholder="body" />
    <input type="button" @click="createPost()" value="submit" />
  </div>
</template>

<script>
export default {
  name: "inputForm"
};
</script>

<style lang="scss" scoped></style>
