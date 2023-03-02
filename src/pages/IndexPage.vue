<template>
  <q-page class="row items-center justify-evenly">
    <q-btn class="col-4" :label="`Palavra: ` + lugar" color="primary" @click="novoLugar"></q-btn>
    <q-btn class="col-4" :label="`Letra: ` + letra" color="primary" @click="novaLetra"></q-btn>
  </q-page>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'IndexPage',
  setup() {
    const letras = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'x', 'w', 'y', 'z']
    const lugares = [
      'shopping',
      'casa',
      'escola',
      'parque',
      'mercado',
      'padaria',
      'farmácia',
      'supermercado',
      'restaurante',
      'cinema',
      'igreja',
      'hospital'
    ]
    const novoLugar = () => {
      lugar.value = lugares[Math.floor(Math.random() * lugares.length)]
    }

    const novaLetra = () => {
      letra.value = letras[Math.floor(Math.random() * letras.length)]
    }

    const letra = ref(letras[Math.floor(Math.random() * letras.length)])
    const lugar = ref(lugares[Math.floor(Math.random() * lugares.length)])

    return {
      novaLetra,
      novoLugar,
      letra,
      lugar
    }
  }
})
</script>
