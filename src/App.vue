<script setup>
import TheBoard from './components/TheBoard.vue'
import TheInstructions from './components/TheInstructions.vue'
import shuffle from './lib/shuffle'
import { ref } from 'vue'

const i = (instruction, card) => ({ instruction, card })
const c = cardString =>
  cards.find(card => card.numero + card.suit.toUpperCase() === cardString)

const cards = [
  { suit: 'fuego', number: 1, symbol: '*' },
  //{ suit: 'fuego', number: 2, symbol: '' },
  { suit: 'fuego', number: 3, symbol: '**' },
  { suit: 'fuego', number: 4, symbol: '' },
  { suit: 'fuego', number: 5, symbol: '††' },
  { suit: 'aire', number: 1, symbol: '' },
  { suit: 'aire', number: 2, symbol: '***' },
  { suit: 'aire', number: 3, symbol: '*' },
  //{ suit: 'aire', number: 4, symbol: '' },
  // { suit: 'aire', number: 5, symbol: '†††' },
  { suit: 'agua', number: 1, symbol: '†' },
  { suit: 'agua', number: 2, symbol: '' },
  { suit: 'agua', number: 3, symbol: '*' },
  { suit: 'agua', number: 4, symbol: '*' },
  { suit: 'agua', number: 5, symbol: '' },
  // { suit: 'tierra', number: 1, symbol: '' },
  { suit: 'tierra', number: 2, symbol: '††' },
  { suit: 'tierra', number: 3, symbol: '†' },
  { suit: 'tierra', number: 4, symbol: '**' },
  { suit: 'tierra', number: 5, symbol: '' },
]
shuffle(cards)
const instructions = [
  i('Del elemento AGUA, la tercera más pequeña', c('3AGUA')),
]

const vCards = ref(cards)
const vInstructions = ref(instructions)
</script>

<template>
  <main>
    <TheBoard :cards="vCards"></TheBoard>
    <TheInstructions :instructions="vInstructions"></TheInstructions>
  </main>
</template>

<style scoped></style>
