<template lang="pug">
aside
  #page-main-aside(:class="showMenu && ['page-main-aside--open']")

    nav.aside-contenidos__body
      .aside-contenidos
        .aside-contenidos__header.d-flex.justify-content-between.align-items-center
          .aside-contenidos__titulo
            h3.mb-0
              i.fa.fa-list-ul.mr-2 
              | Contenidos

          .aside-contenidos__close.d-md-none
            a.page-main-aside__close.icon.btnclose.m-0(@click="$emit('update:showMenu', false)")
      ul#menuMain.menu-main
        template(v-for="(item,index) of menuData")
          li.menu-main__item(:key="`menu-item-${index}`")

            a.menu-main__link(
              v-if="item.hasOwnProperty('download')"
              @click.prevent="descargarZip(item.download)"
            )
              span.menu-main__texto 
                strong {{item.title}}
              span.menu-main__icono
                i(:class="item.icon")

            router-link.menu-main__link(
              v-else
              :to="{name: item.routeName}",
              :class="{'menu-main__link--active' : $route.name == item.routeName}"
            )
              span.menu-main__texto 
                strong {{item.title}}
              span.menu-main__icono
                i(:class="item.icon")
          ul.menu-main.submenu(v-if="item.hasOwnProperty('submenu') && item.submenu.length")
            li.menu-main__item(
              v-for="(subItem, subItemIndex) of item.submenu",
              :key="`submenu-item-${subItemIndex}`"
            )
              router-link.menu-main__link.is-content.routerAnchor(
                :to="{ name: item.routeName , hash: `#${subItem.hash}` }",
                :class="{'menu-main__link--active': $route.hash == `#${subItem.hash}`}"
              )
                span.menu-main__texto {{subItem.title}}
                span.menu-main__icono
                  i(:class="subItem.icon")
          
      ul#menuSecondary.aside-extra.menu-secondary
        li.menu-secondary__item(
          v-for="(secMenuItem, secMenuIndex) of subMenuData",
          :key="`SecMenu-item-${secMenuIndex}`"
        )
          router-link.menu-secondary__link(
            v-if="secMenuItem.hasOwnProperty('routeName')",
            :to="{name: secMenuItem.routeName}"
          )
            i(:class="secMenuItem.icon")
            span.menu-secondary__texto {{secMenuItem.title}}

          a.menu-secondary__link(
            v-else-if="secMenuItem.hasOwnProperty('download')",
            :href="secMenuItem.download",
            target="_blank"
          )
            i(:class="secMenuItem.icon")
            span.menu-secondary__texto {{secMenuItem.title}}

  #page-control.page-control(v-if="!showMenu && $route.path.includes('curso')")
    .row.justify-content-center.align-items-center

      router-link#back.page-control-link.page-control-prev.col.py-3.text-center(
        v-if="controlLinks.back",
        :to="{name: $route.name, hash: `#${controlLinks.back}`}"
      )
        span
          i.fa.fa-chevron-left.mr-3
          | Anterior

      router-link#next.page-control-link.page-control-next.col.py-3.text-center(
        v-if="controlLinks.next" 
        :to="{name: $route.name, hash: `#${controlLinks.next}`}"
      )
        span 
          | Siguiente
          i.fa.fa-chevron-right.ml-3

</template>

<script>
import { menuPrincipal } from '../config/global'
export default {
  name: 'AsideMenu',
  props: {
    showMenu: {
      type: Boolean,
    },
  },
  data: () => ({
    menuData: menuPrincipal && menuPrincipal.menu,
    subMenuData: menuPrincipal && menuPrincipal.subMenu,
  }),
  computed: {
    controlLinks() {
      const menuObject = this.menuData.find(
        item => item.routeName === this.$route.name,
      )
      console.log(this.$route.name)
      if (!menuObject.submenu && !menuObject.submenu.length) {
        return {}
      } else {
        const idxCurrentHash = menuObject.submenu
          .map(item => item.hash)
          .indexOf(this.$route.hash.replace('#', ''))
        if (idxCurrentHash === -1) {
          return {
            next: menuObject.submenu[0].hash,
          }
        } else if (idxCurrentHash === 0) {
          return {
            next: menuObject.submenu[idxCurrentHash + 1].hash,
          }
        } else if (idxCurrentHash === menuObject.submenu.length - 1) {
          return {
            back: menuObject.submenu[idxCurrentHash - 1].hash,
          }
        } else {
          return {
            next: menuObject.submenu[idxCurrentHash + 1].hash,
            back: menuObject.submenu[idxCurrentHash - 1].hash,
          }
        }
      }
    },
  },
  watch: {
    $route(to) {
      if (to.name === 'inicio' && this.showMenu) {
        this.$emit('update:showMenu', false)
      }
    },
  },
  methods: {
    descargarZip(ruta) {
      let url = window.location.href.replace(window.location.hash, '')
      if (url.includes('index.html')) {
        url = url.replace('index.html', '')
      }
      url = url + ruta
      window.open(url, '_blank')
    },
  },
}
</script>

<style lang="sass" scoped>
#page-main-aside
  transition: width 0.5s ease-in-out !important
  width: 0
  height: 100%
  display: flex
  flex-direction: column
  z-index: 1000000000000

.aside-contenidos__body
  height: 100%
  display: flex
  flex-direction: column
  justify-content: space-between

.menu-main
  flex-grow: 1

.aside-extra
  flex-shrink: 0

.menu-main__texto
  line-height: 1em

.page-main-aside
  &--open
    width: 320px !important

.menu-secondary
  width: 100%
  transition: width 0.5s ease-in-out !important
  &--open
    width: 320px !important
</style>
