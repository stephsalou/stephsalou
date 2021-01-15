<template src="./top-bar.html"></template>
<script lang="ts">
import 'reflect-metadata'
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component({
  name: 'TopBar',
})
export default class TopBar extends Vue {
  burgerClass = ''

  showNav() {}
  makeBurgerAnim() {
    this.$refs.burger.classList
  }
}
</script>

<style lang="scss" scoped>
@import './top-bar.scss';
</style>
