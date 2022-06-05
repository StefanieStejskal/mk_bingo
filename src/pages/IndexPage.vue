<template>
  <q-page class="markrei-container text-white text-center">
    <q-img src="MarkreiLogo.png" class="markrei-logo" />
    <div class="text-bold">
      <h4 class="text-uppercase">achtung:</h4>
      Die folgenden Inhalte dienen lediglich zu Unterhaltungszwecken und Support
      unseres lieben Markrei93 auf Twitch, Youtube, TikTok usw.<br />
      Im Idealfall findet auch er es amsüsant, ansonsten darf er sich gerne bei mir
      beschweren kommen - vielleicht werde ich sein Anliegen auch nicht ignorieren.
    </div>
    <q-btn
      class="markrei-btn"
      color="primary"
      label="Let's Play"
      icon="gamepad"
      :to="{ name: 'bingo' }" />
  </q-page>
</template>

<script setup lang="ts">
</script>
