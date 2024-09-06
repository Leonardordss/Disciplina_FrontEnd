<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>Seja bem-vindo à sua página!</p>
    <!-- Exercicio 2 Contador de cliques -->
    <p>Contador: {{ contador }}</p>
    <button @click="incrementar">Clique aqui</button>
    <button @click="limpa">Reset</button>
    <!--Exercicio 3 Mostrar/Ocultar Texto-->
    <p>Mostrar/Ocultar Texto</p>
    <button @click="mostrar = !mostrar"> {{ mostrar ? 'Ocultar Texto' : 'Mostrar Texto' }}</button>
      <!-- Texto exibido apenas se 'mostrar' for verdadeiro -->
      <p v-if="mostrar">Você clicou no botão Texto</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  data() {
    return {
      mostrar: false,
      contador: 0,
    };
  },
  methods: {
    incrementar() {
      this.contador += 1; // Incrementa o valor do contador em 1
    },
    limpa() {
      this.contador = 0;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  margin: 40px 0 0;
}
p {
  margin: 20px 0;
}
button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}
</style>
