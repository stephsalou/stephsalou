<template src="./top-bar.html"></template>
<script lang="ts">
import 'reflect-metadata'
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component({})
export default class TopBar extends Vue {
  burgerClass = ''

  showNav() {
    this.toggleBurgerAnim()
  }
  toggleBurgerAnim() {
    console.dir(this.$refs.burger)
    let BurgerHtmlEl = {} as HTMLDivElement
    let VSection =
      document.getElementById('vertical-section') ?? ({} as HTMLDivElement)
    let HSection =
      document.getElementById('horizontal-section') ?? ({} as HTMLDivElement)
    BurgerHtmlEl = this.$refs.burger as HTMLDivElement
    BurgerHtmlEl.classList.toggle('collapse')
    BurgerHtmlEl.classList.toggle('cross')
    VSection.classList.toggle('show')
    HSection.classList.toggle('show')
  }
}
</script>

<style lang="scss" scoped>
@import './top-bar.scss';
</style>
