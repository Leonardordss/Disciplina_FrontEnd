<template>
  <h2>Exercício 1:  Exibir uma Mensagem</h2>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>Seja bem-vindo à sua página!</p>

    <!-- Exercicio 2 Contador de cliques -->
    <h2>Exercício 2: Contador de Cliques</h2>
    <p>Contador: {{ contador }}</p>
    <button @click="incrementar">Clique aqui</button>
    <button @click="limpa">Reset</button>

    <!-- Exercicio 3 Mostrar/Ocultar Texto -->
    <h2>Exercício 3: Mostrar/Ocultar Texto</h2>
    <p>Mostrar/Ocultar Texto</p>
    <button @click="mostrar = !mostrar"> {{ mostrar ? 'Ocultar Texto' : 'Mostrar Texto' }}</button>
    <p v-if="mostrar">Você clicou no botão Texto</p>

    <!-- Exercicio 4 Lista de Itens -->
    <h2>Exercício 4: Lista de Itens</h2>
    <ul>
      <li v-for="(item, index) in itens" :key="index">{{ item }}</li>
    </ul>

    <!-- Exercicio 5 Campo de Entrada -->
    <h2>Exercício 5: Campo de Entrada</h2>
    <input v-model="nome" placeholder="Digite seu nome" />
    <p>Nome Digitado: {{ nome }}</p>

    <!-- Exercicio 6 Texto Estilizado -->
    <h2>Exercício 6: Texto Estilizado</h2>
    <p class="texto-estilizado">Este é um parágrafo com texto estilizado em verde.</p>
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
      itens: ['Item 1', 'Item 2', 'Item 3'], // Lista de itens
      nome: '', // Propriedade vinculada ao campo de entrada
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
ul {
  list-style-type: none; /* Remove os marcadores padrão da lista */
  padding: 0;
}
li {
  margin: 5px 0; /* Espaçamento entre os itens */
}
input {
  padding: 10px;
  font-size: 16px;
  margin-top: 10px;
  display: block;
}

/* Estilos do Exercício 6 */
.texto-estilizado {
  color: green; /* Cor do texto em verde */
}

/* Adicione estilos para os títulos dos exercícios */
h2 {
  margin-top: 30px;
  border-bottom: 1px solid #ccc;
  padding-bottom: 5px;
  font-size: 20px;
}
</style>
