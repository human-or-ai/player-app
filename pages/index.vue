<template>
  <section class="container">
    <div class="box">
      <h1>Activity Consent</h1>
      <div class="grid-a">
          <div class="row">
            <p>1</p>
            <span>I have received and read the provided Participant Information Sheet.</span>
          </div>
          <div class="row">
            <p>2</p>
            <span>The activity has been fully explained, and I understand what my participation will involve.</span>
          </div>
          <div class="row">
            <p>3</p>
            <span>I understand that my participation is entirely voluntary, and that I am free to withdraw at any time, without giving reason.</span>
          </div>
          <div class="row">
            <p>4</p>
            <span>I understand how the data I provide will be used and stored in the research process.</span>
          </div>
        </div>
        <div class="grid-b">
          <h2>By clicking 'I Agree to Participate', you are confirming that the above requirements have been met.</h2>
          <nuxt-link to="/game" exact>I Agree to Participate</nuxt-link>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
</script>

<style lang="scss" scoped>
@import '../assets/vars';

@keyframes pop-in {
  from {
    transform: translateY(-10%);
    opacity: 0.5;
  }
  to {
    transform: translateY(0);
    opacity: 1;
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
}

.box {
  animation: pop-in 500ms ease-out 1;
  max-width: 900px;
  border: 3px solid $primary;
  border-radius: 3px;
  padding: 1rem;

  > h1 {
    margin: -1rem -1rem 1rem -1rem;
    padding: 1rem;
    font-size: 2rem;
    background: $primary;
  }

  > .grid-a {
    border-radius: 3px;
    overflow: hidden;

    > .row {
      display: flex;
      align-items: center;
      background-color: white;
      padding: 1rem 0;

      > p {
        width: 8rem;
        text-align: center;
        font-size: 2rem;
        color: $secondary;
        font-weight: bold;
      }

      > span {
        flex: 1;
        text-align: left;
      }

      &:nth-child(odd) {
        background-color: darken(white, 5%);
      }
    }
  }

  > .grid-b {
    border-radius: 3px;
    overflow: hidden;
    background-color: $secondary;
    border: 3px solid $primary;
    margin-top: 1rem;
    padding: 1rem;

    display: flex;
    align-items: center;

    > h2 {
      flex: 1;
      color: white;
      font-size: 1rem;
      font-weight: 400;
      text-align: justify;
    }

    > a {
      cursor: pointer;
      padding: 1rem 2rem;
      margin-left: 1rem;
      font-size: 1.2rem;
      font-weight: bold;
      background: linear-gradient(lighten($primary, 5%), $primary);
      border: 4px solid $dark;
      color: $dark;
      border-radius: 1rem;
      text-shadow: 2px 2px 0 rgba(0, 0, 0, 0.1);
      outline: none;
      text-decoration: none;

      &:hover {
        background: white;
        border-color: $primary;
      }
    }
  }
}
</style>
