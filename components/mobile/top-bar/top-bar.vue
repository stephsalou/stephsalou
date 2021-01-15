<template src="./top-bar.html"></template>
<script lang="ts">
import 'reflect-metadata'
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component({
  name: 'TopBar',
})
export default class TopBar extends Vue {
  burgerClass = ''

  showNav() {
    this.makeBurgerAnim()
  }
  makeBurgerAnim() {
    console.dir(this.$refs.burger)
    BurgerHtmlEl = his.$refs.burger
    this.$refs.burger.classList = [
      ...this.$refs.burger.classList,
      'collapse',
      'cross',
    ]
  }
}
</script>

<style lang="scss" scoped>
@import './top-bar.scss';
</style>
