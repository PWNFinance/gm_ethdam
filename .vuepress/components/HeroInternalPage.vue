<!--
  Created by: Carlos E. Salazar <ce.salazar@gmail.com>
  Repository: https://github.com/cesalazar/berlinblockchainweek
  License: MIT
-->

<template>
  <div class="hero">
    <h1>{{ title }}</h1>
    <a class="action-button"
       :href="link"
       target="_blank"
       rel="noopener noreferrer"
       v-if="link && linkText"
    >
      {{ linkText }}
      <OutboundLink />
    </a>
  </div>
</template>

<script>
export default {
  props: ['title', 'link', 'linkText']
}
</script>

<styles scoped lang="stylus">
@require '../theme/styles/config.styl'

.hero
  width 100%
  min-height $internalHeroHeight
  position relative
  background url('/matrix_cube_big.svg')
  background-size cover
  background-position center top
  background-repeat no-repeat
  background-size 100%
  display flex
  flex-direction column
  align-items center
  justify-content space-evenly
  z-index 1
  padding 1.5em 0
  box-sizing border-box
  &:before
    content: ''
    position: absolute
    top: 0
    left: 0
    width: 100%
    height: 100%
  h1
    position: relative
    z-index: 2
    margin 0
    padding 0
    font-size 48px
    max-width $pageContentMaxWidth
    padding 0 1.5rem
  .action-button
    z-index: 2
    margin -2em 0 0
    font-size 18px
    color #fff
    background-color #000
    padding 0.8rem 2rem
    border-radius 5px
    transition all .2s ease-in-out
    border 1px solid white
    box-sizing border-box
    pointer-events all
    &:hover
      color #fff !important
      text-decoration none !important
      border 1px solid $accentColor

@media (max-width: $MQMobileNarrow)
  .hero
    h1
      font-size 2rem
    .action-button
      font-size 1em

</styles>
