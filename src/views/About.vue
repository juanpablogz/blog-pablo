<template>
  <div class="about">
    <carousel />
    <div class="container">
      <h1>Threads y Concurrencia – Ruby</h1>
      <br />
      <h6>publicado el octubre 5,2019 por juan pablo g.</h6>
      <p>En una de mis últimas entrevisatas me preguntaron sobre la concurrencia en Ruby, y si esta realmente existía en dicho lenguaje. Me pareció una pregunta muy interesante; por lo cual, hoy paso a explicar este tema.</p>
      <p>Los Threads han sido siempre un tema muy importante en la programación, donde toda persona que haya estudiado Software sabe lo complejo que es. Por lo que todos sabemos que un programa multithread tiene más de un Thread en ejecución, idealmente en paralelo, en un CPU multicore. Sin embargo, cuando esto no es posible, se simula esta caraterística. En el caso de Ruby, la implementación va cambiando según la versión. Por ejemplo, en Ruby 1.8 solamente se permite un Thread nativo, donde todos los Threads de Ruby corren sobre él. Por lo tanto, en esta versión, no existe el paralelismo realmente. Sin embargo, Ruby 1.9 permite tener un Thread nativo por cada uno de los del lenguaje. A partir de esto, ya podemos observar que Ruby no siempre ofrece paralelismo realmente (Una característica muy deseable si usamos Threads).</p>
    </div>
  </div>
</template>
<script>
import carousel from "../components/carousel";
export default {
  components: {
    carousel
  }
};
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