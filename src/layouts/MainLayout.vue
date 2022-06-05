<template>
  <q-layout view="lHh Lpr lFf">
    <MarkreiHeader/>
    <q-page-container class="bg-dark markrei-container__page">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts">
import MarkreiHeader from '../components/MarkreiHeader.vue';
</script>
