<template>
  <q-page class="markrei-container text-white text-center">
    <h5 class="text-uppercase text-bold">
      Willkommen beim offiziellen Markrei93 Bingo:
    </h5>
    Die Regeln sind sehr simpel - da unser liebenswerter <span class="text-bold">Markrei93</span>
    bekanntlich <span class="text-uppercase">jeden Tag</span> streamed, passieren ihm dabei
    gerne einmal so manche Missgeschicke. Wir die Community möchten uns für seine tägliche Arbeit
    in dieser Form bedanken, indem wir ihm dieses Spiel widmen, damit man seinen Stream
    umso mehr genießen kann.<br />
    <span class="text-bold">
      Ein Game für einen Gamingstreamer => eigentlich doch ganz passend ;)
    </span>

    <div class="bingo-container">
      <div class="row justify-between">
        <div class="bingo-container__item"></div>
        <div class="bingo-container__item bingo-container__item-header">B</div>
        <div class="bingo-container__item bingo-container__item-header">I</div>
        <div class="bingo-container__item bingo-container__item-header">N</div>
        <div class="bingo-container__item bingo-container__item-header">G</div>
        <div class="bingo-container__item bingo-container__item-header">O</div>
        <div class="bingo-container__item bingo-container__item-header">B</div>
        <div
          v-for="element in firstBlock"
          :key="element"
          class="bingo-container__item"
          @click="setCheck(element.id)"
          :id="element.id">
          {{ element.description }}
        </div>
        <div class="bingo-container__item bingo-container__item-header">I</div>
        <div
          v-for="element in secondBlock"
          :key="element"
          class="bingo-container__item"
          @click="setCheck(element.id)"
          :id="element.id">
          {{ element.description }}
        </div>
        <div class="bingo-container__item bingo-container__item-header">N</div>
        <div
          v-for="element in thirdBlock"
          :key="element"
          class="bingo-container__item"
          @click="setCheck(element.id)"
          :id="element.id">
          {{ element.description }}
        </div>
        <div class="bingo-container__item bingo-container__item-header">G</div>
        <div
          v-for="element in fourthBlock"
          :key="element"
          class="bingo-container__item"
          @click="setCheck(element.id)"
          :id="element.id">
          {{ element.description }}
        </div>
        <div class="bingo-container__item bingo-container__item-header">O</div>
        <div
          v-for="element in fifthBlock"
          :key="element"
          class="bingo-container__item"
          @click="setCheck(element.id)"
          :id="element.id">
          {{ element.description }}
        </div>
      </div>
    </div>
  </q-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { bingoData } from 'src/data/bingoData';

const firstBlock = ref<{ id: number; description: string; }[]>([]);
const secondBlock = ref<{ id: number; description: string; }[]>([]);
const thirdBlock = ref<{ id: number; description: string; }[]>([]);
const fourthBlock = ref<{ id: number; description: string; }[]>([]);
const fifthBlock = ref<{ id: number; description: string; }[]>([]);

for (let i = 0; i < 5; i += 1) {
  firstBlock.value.push(bingoData[i]);
}

for (let i = 5; i < 10; i += 1) {
  secondBlock.value.push(bingoData[i]);
}

for (let i = 10; i < 15; i += 1) {
  thirdBlock.value.push(bingoData[i]);
}

for (let i = 15; i < 20; i += 1) {
  fourthBlock.value.push(bingoData[i]);
}

for (let i = 20; i < 25; i += 1) {
  fifthBlock.value.push(bingoData[i]);
}

function setCheck(id: number) {
  const element = document.getElementById(`${id}`);
  element.classList.add('bingo-container__item--checked');
}
</script>

<style lang="scss" scoped>
.bingo-container {
  margin: 64px 0;

  &__item {
    display: flex;
    justify-content: center;
    align-items: center;
    border: 2px solid $primary;
    margin-bottom: 16px;
    padding: 2% 1%;
    width: 15%;
    transition: 0.25s;

    &:hover {
      cursor: pointer;
      background-color: $primary;
    }

    &--checked {
      background-color: $primary;
    }

    &-header {
      font-size: 2rem;

      &:hover {
        cursor: auto;
        background-color: transparent;
      }
    }

    &:first-of-type {
      border: none;

      &:hover {
        cursor: auto;
        background-color: transparent;
      }
    }
  }
}
</style>
