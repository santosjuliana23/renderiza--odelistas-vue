<script setup>
import { ref } from 'vue'

const novoItem = ref('')
const listaCidades = ref([
  'São Paulo',
  'Rio de Janeiro',
  'Belo Horizonte',
  'Salvador',
  'Fortaleza',
  'Curitiba',
  'Manaus',
  'Recife',
  'Porto Alegre',
  'Brasília'
])

function adicionar() {
  listaCidades.value.push(novoItem.value)
  novoItem.value = ''
}

//ORDEM ALFABÉTICA
const novoItem2 = ref('')
const listaCidades2 = ref([
  'São Paulo',
  'Rio de Janeiro',
  'Belo Horizonte',
  'Salvador',
  'Fortaleza',
  'Curitiba',
  'Manaus',
  'Recife',
  'Porto Alegre',
  'Brasília'
])

function adicionar2() {
  novoItem2.value = novoItem2.value[0].toUpperCase() + novoItem2.value.slice(1)
  listaCidades2.value.push(novoItem2.value)
  novoItem2.value = ''
}
</script>
<template>
  <div class="primeiro">
    <p>Ordem não-alfabética</p>
    <input type="text" v-model="novoItem" />
    <button id="botao" @click="adicionar">Adicionar</button>
    <ul>
      <li v-for="item in listaCidades">{{ item }}</li>
    </ul>
  </div>
  <div class="segundo">
    <p>Ordem Alfabética</p>
    <input type="text" v-model="novoItem2" />
    <button id="botaoalfabetico" @click="adicionar2">Adicionar</button>
    <ul>
      <li v-for="item2 in listaCidades2.sort()">{{ item2 }}</li>
    </ul>
  </div>
</template>

<style setup>
#botaoalfabetico {
  width: 130px;
  height: 30px;
  background-color: lightpink;
  border: rgb(201, 69, 91);
  border-width: 2px;
  border-style: solid;
  border-radius: 20px;
}

#botao {
  width: 130px;
  height: 30px;
  background-color: lightpink;
  border: rgb(201, 69, 91);
  border-width: 2px;
  border-style: solid;
  border-radius: 20px;
}

.primeiro {
  margin-right: 50px;
}
</style>
