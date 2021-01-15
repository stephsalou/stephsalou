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
    this.toggleBurgerAnim()
  }
  toggleBurgerAnim() {
    console.dir(this.$refs.burger)
    let BurgerHtmlEl = {} as HTMLDivElement
    let VSection = document.getElementById('vertical-section')
    let HSection = document.getElementById('horizontal-section')
    BurgerHtmlEl = this.$refs.burger as HTMLDivElement
    BurgerHtmlEl.classList.toggle('collapse')
    BurgerHtmlEl.classList.toggle('cross')
  }
}
</script>

<style lang="scss" scoped>
@import './top-bar.scss';
</style>
