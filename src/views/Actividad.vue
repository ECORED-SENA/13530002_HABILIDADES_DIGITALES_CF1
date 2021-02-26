<template lang="pug">
.container

  .header-ecored
    h1 Actividad didáctica


  .row.align-items-center.justify-content-center.my-5
    .col-8.col-md-5.col-xl-4.mb-5
      figure
        img(src="@/assets/images/pages/actividad/img_actividad.svg", alt="")
    
    .col-12.col-md-7
      hr.line-100.bg-orange
      .text-center.p-2
        h2 ¡Ponga a prueba su conocimiento! 
        p La siguiente actividad tiene como propósito validar los conocimientos relacionados con el tema 
          strong Empezando el aprendizaje, dispositivos y TIC.
        a.btn.btn-colour-Orange(href="" @click.prevent="abrirActividades") Iniciar
      hr.line-100.bg-orange
    
</template>

<script>
export default {
  name: 'Actividad',
  methods: {
    abrirActividades() {
      let url = window.location.href.replace(window.location.hash, '')
      if (url.includes('index.html')) {
        url = url.replace('index.html', '') + 'actividades/index.html'
      } else {
        url = url + 'actividades/'
      }
      window.open(url, '_blank')
    },
  },
}
</script>

<style lang="scss" scoped></style>
