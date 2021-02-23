<template lang="pug">
.curso-portada
  .container
    .row.align-items-center
      .col-12.col-lg-6

        h3#curso-titulo-componente.curso-subtitulo {{globalData.subtituloPrincipal}}
        h1#curso-titulo-tema.curso-titulo {{globalData.tituloPrincipal}}

        .brand-line-primary

        template(v-if="$route.path.includes('curso')")
          .keywords(v-if="selectedMenuItem.hasOwnProperty('tags')")
            span.badge.badge-pill.badge-light.mr-2(v-for="tag of selectedMenuItem.tags" :ref="'tag-'+tag") {{'#'+tag}}

          .barra-dots.mt-5
            img.img-fluid(src='@/assets/images/header/icon_dots.svg', alt='alt')

        template(v-else)
          p.curso-descripcion {{globalData.descripcionCurso}}

        template(v-if="$route.name === 'inicio'")
          router-link.curso-btn-iniciar.btn.btn-light(:to="{name: 'curso'}")
            span Iniciar curso

      .col-12.col-lg-6.text-center
        .d-none.d-lg-block
          img.curso-imagen(:src="globalData.imagen")

</template>

<script>
import { global } from '../config/global'
export default {
  name: 'HeaderComponent',
  props: {
    selectedMenuItem: {
      type: Object,
      default: () => ({}),
    },
  },
  data: () => ({
    globalData: global,
    imagen: require('@/assets/images/pages/ilustraciones/group16263.svg'),
  }),
}
</script>
<style scoped lang="sass">
.curso-portada
  padding: 2rem 2rem 2rem

.badge
  background-color: $tags-bg-color
</style>
