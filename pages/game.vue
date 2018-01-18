<template>
  <section class="container">
    <div class="canvas">
      <canvas ref="canvas"></canvas>
    </div>
    <div class="controls">
      <button>Reset</button>
      <nuxt-link to="/">Back</nuxt-link>
    </div>
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

<style lang="scss" scoped>
@import '../assets/vars';

@keyframes pop-in {
  from {
    transform: scale(0);
  }
  to {
    transform: scale(1);
  }
}

.container {
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-color: $dark;

  > .canvas {
    display: flex;
    align-items: center;
    justify-content: center;
    flex: 1;

    > canvas {
      animation: pop-in 500ms ease-out;
      border: 4px solid $primary;
      box-shadow: 8px 8px 0 rgba(0, 0, 0, 0.2);
      background: white;
    }
  }

  > .controls {
    width: 100%;
    background: rgba(0, 0, 0, 0.1);
    padding: 1rem;
    display: flex;
    align-items: stretch;
    justify-content: center;

    button,
    a {
      transition: background 150ms ease-out, color 150ms ease-out,
        border-color 150ms ease-out;
      cursor: pointer;
      background: $dark;
      color: rgba($primary, 0.2);
      border: 3px solid rgba($primary, 0.2);
      font-weight: bold;
      padding: 0.25rem 0.5rem;
      border-radius: 3px;
      text-decoration: none;
      outline: none;
      font-size: 1rem;
      margin: 0 0.5rem;
    }

    &:hover {
      button,
      a {
        border-color: $primary;
        color: $primary;
        &:hover {
          color: $dark;
          background: $primary;
        }
      }
    }
  }
}
</style>
