<script setup>
//Aqui fica a lógica
import curtir from "../src/assets/heart-icon.png";
import curtido from "../src/assets/heart-icon1.png";
import { ref } from "vue";

// Criamos um estado reativo para cada imagem
const curtidoEstado1 = ref(false); // Estado para a primeira seção
const curtidoEstado2 = ref(false); // Estado para a segunda seção
const curtidoEstado3 = ref(false); // Estado para a terceira seção
</script>

<template>
  <!-- Aqui fica a estrutura do site como num html -->
  <header>
    <h1><span>V</span>ue</h1>
    <h6>(Se pronuncia view-viu?)</h6>
    <input type="text" placeholder="Pesquisa no blog" />
  </header>
  <main>
    <section>
      <div>
        <h5>Definição</h5>
        <!-- Como trazer dados de forma dinâmica?
        <p>{}</p> 
       Para inserir de atributos como src , usamos o v-bind ou usando o : , : é um atalho para o v-bind se n usasse o atalho ficaria v-bind:src="curtir"
        -->
        <!-- Alterando a imagem dinamicamente com @click -->
        <img
          :src="curtidoEstado1 ? curtido : curtir"
          alt="Botão de Curtida"
          @click="curtidoEstado1 = !curtidoEstado1"
        />
      </div>
      <h3>O que é Vue.js?</h3>
      <p>
        Vue.js é um framework JavaScript progressivo usado para criar interfaces
        de usuário dinâmicas e reativas. Ele permite combinar HTML, CSS e JS de
        forma eficiente, sendo ideal para criar aplicações modernas, desde
        pequenos widgets até sistemas completos.
      </p>
    </section>
    <section>
      <div>
        <h5>Curiosidade</h5>

        <img
          :src="curtidoEstado2 ? curtido : curtir"
          alt="Botão de Curtida"
          @click="curtidoEstado2 = !curtidoEstado2"
        />
      </div>
      <h3>A Origem do Vue.js</h3>
      <p>
        Vue.js foi criado por Evan You, um ex-desenvolvedor do Google, em 2014.
        Ele queria uma ferramenta leve e flexível que combinasse o melhor do
        AngularJS e do React, mas sem a complexidade deles. O resultado? Um
        framework que conquistou a comunidade rapidamente.
      </p>
    </section>
    <section>
      <div>
        <h5>Funcionalidade</h5>
        <img
          :src="curtidoEstado3 ? curtido : curtir"
          alt="Botão de Curtida"
          @click="curtidoEstado3 = !curtidoEstado3"
        />
        
        
      </div>
      <h3>Como funciona a reatividade no Vue.js?</h3>
      <p>
        No Vue.js, a reatividade é central: mudanças nos dados atualizam
        automaticamente a interface. Isso é possível graças ao Virtual DOM e à
        capacidade do Vue de rastrear dependências, economizando esforço manual
        para sincronizar o estado e o visual.
      </p>
    </section>
  </main>
</template>

<style scoped lang="scss">
/* e aqui fica o estilo */

header {
  background-color: #17171a;
  font-family: "Space Grotesk", sans-serif;
  color: #ffffff;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 100vw;
  height: 20vh;

  h1 {
    font-size: 2.5rem;
    span {
      color: #39ff14;
    }
  }

  input {
    width: 60vw;
    background-color: #252529;
    border: none;
    margin-top: 1rem;
    padding: 8px 0;

    &::placeholder {
      padding-left: 10px;
    }
  }
}
main {
  font-family: "Space Grotesk", sans-serif;
  background-color: #121214;
  height: 80vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 5rem;

  section {
    border: #252529 solid;
    border-radius: 5px;
    width: 85vw;
    height: 24vh;
    padding: 1.8rem;
    margin: 1.2rem;
    &:hover {
      border: solid #39ff14;
    }
    div {
      display: flex;
      justify-content: space-between;
      color: #17171a;
      img {
        cursor: pointer;
        height: 32px;
      }
    }
    h5 {
      color: #39ff14;
      font-size: 1rem;
    }
    h3 {
      color: #ffffff;
      font-size: 1.5rem;
    }
    P {
      color: #afabb6;
      font-size: 1.25rem;
      margin: 10px 0;
    }
  }
}
</style>
