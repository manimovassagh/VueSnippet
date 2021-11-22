<template>
  <div>
    <div v-for="post in posts" :key="post.id">
      <h3>{{ post.id }}<br/>{{ post.title }}<br/>{{post.body}}</h3>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  created() {
    this.fetchDataFrom();
  },
  data() {
    return {
      posts: [],
    };
  },
  methods: {
    fetchDataFrom() {
      axios
        .get("https://jsonplaceholder.typicode.com/posts")
        .then((response) => (this.posts = response.data))
        .catch((err) => console.log(err));
    },
  },
};
</script>

<style>
</style>