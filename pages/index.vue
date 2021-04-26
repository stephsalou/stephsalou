<template>
  <div class="container flex flex-col justify-center h-full">
    <top-bar />
    <h1 class="name-container">
      <span
        class="name-letter"
        :class="welcomeWords.includes(letter) ? 'hover:shadow' : null"
        v-for="(letter, index) in welcomeText.split('')"
        :key="index.toString()"
        >{{ letter }}</span
      >
    </h1>
  </div>
</template>

<script lang="ts">
import TopBar from '~/components/mobile/top-bar/top-bar.vue'

import { Component, Vue } from 'nuxt-property-decorator'
import Logo from '@/components/Logo.vue'
@Component({
  name: 'index',
  components: {
    TopBar,
  },
})
export default class Index extends Vue {
  welcomeText = "Hello world i'm stephane salou"

  get welcomeWords(): string[] {
    return this.welcomeText
      .split('')
      .filter((letter: String) => (letter ? letter != ' ' : ''))
  }
}
</script>

<style lang="scss">
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
.name-container {
  letter-spacing: 4px;
  .name-letter {
    font-size: 2rem;
    &::selection {
      color: red;
      background-image: url('../assets/image/codebinaire.jpg');
    }
    &:hover {
      font-size: 3.5rem;
      background: rgb(36, 10, 0);
      cursor: pointer;
      background: radial-gradient(
        circle,
        rgba(36, 10, 0, 1) 0%,
        rgba(104, 121, 9, 1) 46%,
        rgba(27, 0, 255, 0.6937149859943977) 100%
      );
      margin: 0.45rem;
    }
  }
}
</style>
