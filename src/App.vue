<template>
  <div>
    <b-navbar toggleable="lg" type="dark" class="color">
      <b-navbar-brand href="#">
        <img src="https://img.icons8.com/dusk/38/000000/briefcase.png" />
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item a href="#welcome" to="/" class="index">Inicio</b-nav-item>
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-nav-form>
            <b-button variant="link" to="/form">crear post</b-button>
            <b-button variant="link" to="sign-up">aprendiendo con</b-button>
          </b-nav-form>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>

    <router-view />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import carousel from "./components/carousel";
import axios from "axios";
export default {
  name: "App",

  components: {
    HelloWorld,
    carousel
  },

  data: () => ({}),
  methods: {
    getPost() {
      axios.get("/posts").then(response => {
        console.log(response.data);
      });
    }
  }
};
</script>

<style>
.v-application--wrap {
  min-height: 70vh !important;
}
.container {
  margin-top: 0px;
  padding: 0px !important;
}
.color {
  background-color: #006ba6 !important;
  padding: 0.2rem 1.2rem;
}
.btn-link {
  color: #fffcff;
}
.index {
  color: #fffcff;
}
</style>