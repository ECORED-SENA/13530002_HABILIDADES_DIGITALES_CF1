<template lang="pug">

.container

  .header-ecored
    h1 Referencias bibliográficas

  .jumbotron.bg-white.referencias
    template(v-for="(item, index) of referencias")
      p(:ref="'referencia-'+index") {{item.referencia}}
        a(:href="item.enlace", target="_blank").ml-2 
          | {{item.tituloenlace.length ? item.tituloenlace : item.enlace}}
      hr

    .row.justify-content-betwee

      .col-12.col-lg-6.mb-3.mb-lg-0
        .jumbotron.d-flex.align-items-center.p-4
          .row.flex-fill.align-items-center
            .col-2
              p.mb-0.text-center
                i.fa.fa-picture-o.fa-2x.text-center
            .col-10
              p.mb-0.text-center Fotografías y vectores tomados de <a class="text-small" href="https://www.shutterstock.com/" target="_blank">https://www.shutterstock.com/</a> y <a class="text-small" href="https://www.freepik.es/" target="_blank">https://www.freepik.es/</a>

      .col-12.col-lg-6
        .jumbotron.d-flex.align-items-center.p-4
          .row.flex-fill.align-items-center
            .col-2
              p.mb-0.text-center.pl-4
                i.fa.fa-creative-commons.fa-2x.text-center
            .col-10
              p.mb-0.text-center Licencia Creative Commons <br> <strong>CC BY-NC-SA</strong><br> <a class="text-small" href="https://creativecommons.org/licenses/by-nc-sa/3.0/es/" target="_blank">Ver licencia.</a>            
</template>

<script>
import { referencias } from '../config/global'
export default {
  name: 'Referencias',
  data: () => ({
    referencias: referencias,
  }),
}
</script>

<style lang="sass" scoped>
.jumbotron
  height: 100%
  margin: 0
</style>
