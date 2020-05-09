
<template>
  <div id="app">
    <v-app id="inspire">
      <v-carousel>
        <v-carousel-item
          v-for="(item,i) in items"
          :key="i"
          :src="item.src"
          reverse-transition="fade-transition"
          transition="fade-transition"
          h
        ></v-carousel-item>
      </v-carousel>
    </v-app>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          src:
            "https://images.unsplash.com/photo-1550645612-83f5d594b671?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80"
        },
        {
          src:
            "https://images.unsplash.com/photo-1484417894907-623942c8ee29?ixlib=rb-1.2.1&auto=format&fit=crop&w=1489&q=80"
        },
        {
          src:
            "https://images.unsplash.com/photo-1569748130764-3fed0c102c59?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80"
        }
      ]
    };
  },
  methods: {}
};

name: "carousel";
</script>

<style scoped>
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