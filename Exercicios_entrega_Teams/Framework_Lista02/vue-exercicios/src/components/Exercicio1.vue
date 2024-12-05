<template>
  <div id="app">
    <h1>Exercícios Framework Vue.js Lista 02</h1>

    <!-- Exercício 1: Contador de Cliques -->
    <section>
      <h2>Contador de Cliques</h2>
      <p>{{ contador }}</p>
      <button @click="incrementar">Incrementar</button>
      <button @click="decrementar">Decrementar</button>
    </section>

    <!-- Exercício 2: Mostrar/Ocultar Texto -->
    <section>
      <h2>Mostrar/Ocultar Texto</h2>
      <button @click="mostrarTexto = !mostrarTexto">
        {{ mostrarTexto ? 'Ocultar' : 'Mostrar' }} Texto
      </button>
      <p v-if="mostrarTexto">Este é o texto mostrado ou ocultado!</p>
    </section>

    <!-- Exercício 3: Lista Dinâmica -->
    <section>
      <h2>Lista Dinâmica</h2>
      <input v-model="novoItem" @keyup.enter="adicionarItem" placeholder="Adicione um item" />
      <ul>
        <li v-for="(item, index) in itens" :key="index" @click="removerItem(index)">
          {{ item }}
        </li>
      </ul>
    </section>

    <!-- Exercício 4: Input de Nome -->
    <section>
      <h2>Input de Nome</h2>
      <input v-model="nome" placeholder="Digite seu nome" />
      <p v-if="nome">Bem-vindo, {{ nome }}!</p>
    </section>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      // Exercício 1
      contador: 0,

      // Exercício 2
      mostrarTexto: false,

      // Exercício 3
      novoItem: '',
      itens: [],

      // Exercício 4
      nome: ''
    };
  },
  methods: {
    // Exercício 1
    incrementar() {
      this.contador++;
    },
    decrementar() {
      this.contador--;
    },

    // Exercício 2
    // Já controlado por v-if e no botão com toggle

    // Exercício 3
    adicionarItem() {
      if (this.novoItem.trim() !== '') {
        this.itens.push(this.novoItem);
        this.novoItem = ''; // Limpa o campo de entrada após adicionar
      }
    },
    removerItem(index) {
      this.itens.splice(index, 1); // Remove o item da lista
    },

    // Exercício 4
    // Já controlado por v-model
  }
};
</script>

<style>
section {
  margin-bottom: 20px;
}

button {
  margin: 5px;
}

input {
  margin-bottom: 10px;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  cursor: pointer;
  margin: 5px 0;
  padding: 5px;
  background-color: #f0f0f0;
}

li:hover {
  background-color: #ccc;
}
</style>
