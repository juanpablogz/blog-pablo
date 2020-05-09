<template>
  <div>
    <div class="container">
      <v-text-field label="titulo" v-model="post.title"></v-text-field>
      <v-textarea
        background-color="amber lighten-4"
        color="orange orange-darken-5"
        label="parrafo 1"
        v-model="post.subtitle"
      ></v-textarea>
      <v-textarea
        background-color="amber lighten-4"
        color="orange orange-darken-5"
        label="parrafo 2"
        v-model="post.body"
      ></v-textarea>
      <v-file-input accept="image/*" label="Subir imagen"></v-file-input>
      <b-button variant="outline-primary" @click="agregarPost(post)">Publicar post</b-button>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      posts: [],
      post: { title: "", subtitle: "", body: "" }
    };
  },
  methods: {
    agregarPost() {
      this.axios
        .post("/posts", this.post)
        .then(response => {
          console.log(response.data);
          this.posts.push(response.data);
          this.post.title = "";
          this.post.subtitle = "";
          this.post.body = "";
          // this.showAlert();
          // this.mensaje.color = "success";
          // this.mensaje.texto = "Agregado correctamente";
        })
        .catch(e => {
          console.log(e.response.data.error.errors.nombre.message);
          // Alerta de mensaje
          // this.showAlert();
          // this.mensaje.color = "danger";
          // this.mensaje.texto = e.response.data.error.errors.nombre.message;
        });
    }
  }
};
</script>

<style>
</style>