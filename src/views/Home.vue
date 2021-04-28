<template>
  <div id="home-page">
      <Tamagochi />
  </div>
</template>

<script>
import Tamagochi from '@/components/Tamagochi.vue';
export default {
components: {
    Tamagochi
}
}
</script>

<style lang="scss">
    #home-page {
        background: lightskyblue;
        min-height: calc(100vh - 40px);
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>