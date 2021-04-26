<template>
  <div class="container flex flex-col justify-center h-full">
    <top-bar />
    <h1>
      <span
        class="NameLetter"
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

<style>
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
</style>
