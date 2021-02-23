<template lang="pug">

div(:class="$route.name === 'inicio' ? ['container'] : ['container-fluid']")

  .topbar.d-flex.justify-content-between.align-items-center(:class="topBarClasses")

    .topbar__logo
      img(src="@/assets/images/logos/senaLogo.svg")

    .topbar__menu(:class="$route.name === 'inicio' && ['d-md-none']")
      a.topbar__menu__btn.btn-menu-responsive(@click="$emit('update:showMenu', !showMenu)" :class="showMenu && ['active']")
        span
        span
        span

      span.topbar__menu__title(v-if="$route.name != 'inicio'") MENÚ

    nav#topbar__nav.topbar__nav.collapse.show.d-none.d-md-block(v-if="$route.name === 'inicio'")
  
      ul.topbar__list

        li.topbar__item
          a.topbar__link(href="#ResultadosAprendizaje")
            span.text-white Resultados de aprendizaje

        li.topbar__item
          a.topbar__link(href="#IndiceTematico")
            span.text-white Contenidos

        li.topbar__item
          a.topbar__link(href="#Creditos")
            span.text-white Créditos
</template>

<script>
export default {
  name: 'OverHeader',
  props: {
    showMenu: {
      type: Boolean,
    },
  },
  computed: {
    topBarClasses() {
      const newClasses = []
      if (this.$route.name != 'inicio') {
        newClasses.push('topbar--fixed', 'flex-row-reverse')
      }
      if (this.showMenu) {
        newClasses.push('topbar--open')
      }
      return newClasses
    },
  },
}
</script>

<style lang="sass" scoped>
// @import "@/assets/scss/base/_variables.scss"
.container-fluid,.container
  padding: 0
  margin-top: 65px
.topbar
  margin-bottom: 2rem
  padding-top: 1rem
  transition: width 0.5s ease-in-out
  max-height: 65px
  z-index: 1000000000

  &--fixed
    padding: 0.5rem 1rem
    margin-bottom: 2rem
    padding-top: 0
    top: 0
    background-color: $white
    position: fixed
    width: 100%

  &--open
    width: calc(100% - 320px)

  &__logo
    img

      width: 50px

  &__nav
    display: block

  &__list
    list-style: none
    padding: 0
    margin: 0
    display: flex
    justify-content: space-between
    align-items: center
    width: 450px

  &__link
    color: $base-color-dark

  &__menu
    position: relative


    &__btn
      background: none
      display: block

    &__title
      bottom: 0
      display: block
      font-size: .7em
      line-height: 1em
      text-align: center


  @media screen and (max-width: $breakpoint-small)

    padding: 0.5rem 1rem
    margin-bottom: 2rem
    // margin-top: -2rem
    // margin-left: -2rem
    // margin-right: -2rem
    background-color: $white

    &__logo

    &__menu
      &__btn
        color: $base-color-dark

    &__nav
      flex: 1 1 100%

      &__list
        flex-direction: column
        margin-top: .5rem
        width: 100%

      &__item
        width: 100%

        &:hover
          background-color: $gray-200

      &__link
        display: block
        padding: .8rem 0
        text-align: center
        border-bottom: 1px solid $base-border-color
</style>
