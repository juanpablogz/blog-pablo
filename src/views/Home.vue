<template>
  <div class="about">
    <carousel />
    <div class="container">
      <div v-for="posts in this.post" :key="posts.id">
        <h1>{{posts.title}}</h1>
        <br />
        <h6>{{posts.subtitle}}</h6>
        <p>{{posts.body}}</p>
        <p></p>
      </div>
    </div>
  </div>
</template>
<script>
import carousel from "../components/carousel";
import axios from "axios";
export default {
  data() {
    return {
      post: []
    };
  },
  components: {
    carousel
  },
  mounted() {
    axios.get("/posts").then(response => {
      console.log(response.data);
      this.post = response.data;
    });
  }
};
</script>
<style scoped>
.container {
  text-align: center;
}
body {
  font-size: 62.5%;
}

h1 {
  margin-top: 25px;
  font-size: 2em; /* 2em = 2 x 10px = 20px */
}
p {
  font-size: 1.4em; /* 1.4em x 10px = 14px */
}
</style>