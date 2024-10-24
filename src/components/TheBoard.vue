<script setup>
import { defineProps } from 'vue'

defineProps({ cards: Array })
</script>

<template>
  <div class="board">
    <div class="row row-cols-4 card-line">
      <div class="col" v-for="(card, index) in cards" :key="index">
        <div :class="['card', card.suit]">
          <div class="symbol">{{ card.symbol }}</div>
          <div class="number">{{ card.number }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.board {
  max-width: 580px;
  margin: auto;
  margin-top: 20px;
}
.card {
  position: relative; /* Necesario para que el símbolo se posicione correctamente dentro de la carta */
  margin-top: 10px;
  color: #fff;
  font-size: 40px;
  width: 140px;
  height: 180px;
  padding: 0.5rem;
  font-weight: bold;
  display: flex;
  align-items: flex-end;
  justify-content: center;
}

.symbol {
  position: absolute;
  top: 5px;
  right: 5px;
  font-size: 30px;
}
.number {
  position: absolute;
  top: 0px;
  left: 10px;
  font-size: 40px;
}
.fuego {
  background-color: #b02015;
  background-image: url(../assets/palos/fuego.png);
  background-position: center;
  background-size: cover;
}
.aire {
  background-color: #7c11ce;
  background-image: url(../assets/palos/aire.png);
  background-position: center;
  background-size: cover;
}
.agua {
  background-color: #155db0;
  background-image: url(../assets/palos/agua.png);
  background-position: center;
  background-size: cover;
}
.tierra {
  background-color: #2fb015;
  background-image: url(../assets/palos/tierra.png);
  background-position: center;
  background-size: cover;
}
</style>
