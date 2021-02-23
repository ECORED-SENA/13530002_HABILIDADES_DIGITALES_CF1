<template lang="pug">
.inicio
  section#ResultadosAprendizaje.curso-resultados.section.bg-base-light
    .container
      h2  Resultados de 
        br
        | aprendizaje
      .brand-line-primary

      .card.resultado-item
        .card-body
          ul.bg-color-dark.mb-0
            li.mb-0
              span Seleccionar información y recursos digitales teniendo en cuenta herramientas y protocolos de búsqueda.

  section#IndiceTematico.curso-indice-tematico.section
    .container
      h2 Desarrollo de 
        br 
        | contenidos
      .brand-line-primary

      .row.justify-content-center
        .col-12.col-sm-10

          .card.wow.flipInX(data-wow-delay=".4s")
              
            .card-body

              ul.list-group.list-group-flush.list.my-n3.nav-temas(v-for="item of desarrolloDeContenidos")
                li.list-group-item.nav-tema-item
                  .row.align-items-center
                    .col-auto
                      .avatar.avatar-sm
                        span.nav-tema-item__icon.avatar-title.font-size-lg.bg-secondary-soft.rounded-circle.text-primary.font-weight-bold 
                          i(v-if="getIcon(item.type) != item.type" :class="getIcon(item.type)")
                          template(v-else) {{getIcon(item.type)}}

                    .col.ml-n2
                      span.nav-tema-item__titulo 
                        router-link(:to="item.route") {{item.title}}
                    .col-auto
                      router-link.btn.btn-light.nav-tema-item__btn(:to="item.route") Ver más
  Creditos
</template>

<script>
import { desarrolloDeContenidos } from '../config/global'
import Creditos from '../components/Creditos'
export default {
  name: 'Inicio',
  components: { Creditos },
  data: () => ({
    desarrolloDeContenidos: desarrolloDeContenidos,
  }),
  methods: {
    getIcon(type) {
      switch (type) {
        case 'play':
          return 'fa fa-play'
        case 'question':
          return 'fa fa-question'
        case 'text':
          return 'fa fa-file-text-o'
        case 'folder':
          return 'fa fa-folder-open'
        case 'references':
          return 'fa fa-book'
        case 'glosary':
          return 'fa fa-sort-alpha-asc'
        default:
          return type
      }
    },
  },
}
</script>
