<template>
  <section class="container">
    <canvas ref="canvas"></canvas>
  </section>
</template>

<script>
import Game from '@varbrad/hoai-game'

export default {
  data() {
    return {
      game: null
    }
  },
  mounted() {
    this.game = new Game(this.$refs.canvas, 640, 480)
  }
}
</script>

<style lang="scss">
$dark: #314256;
$primary: #f1e202;

.container {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-color: $dark;

  > canvas {
    border: 4px solid $primary;
    box-shadow: 8px 8px 0 rgba(0, 0, 0, 0.2);
    background: white;
  }
}
</style>
