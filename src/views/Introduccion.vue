<template lang="pug">
.container#page-introduccion

  .header-ecored
    h1 Introducción


  .jumbotron.bg-white 
    .row
      .col
        .card
          .embed-responsive.embed-responsive-16by9
            iframe.embed-responsive-item(width='560', height='315', src='https://www.youtube.com/embed/bv8zTM9mZZ8', frameborder='0', allow='accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture', allowfullscreen='')
          .card-body.mt-0
            p El aprendiz apropiará conocimientos de la normativa del proceso ECCL y reconocerá los referentes de evaluación de acuerdo con lineamientos del organismo certificador.

        .p-5(style="background-color:#ECEFFE")        
          p El Servicio Nacional de Aprendizaje- SENA, mediante el Artículo 12, del Decreto 249 de 2004, es el responsable en Colombia de evaluar y certificar las competencias laborales de los colombianos y a través del Artículo 19 del Decreto 933 de 2003 está autorizado para evaluar y certificar las competencias laborales: "El Servicio Nacional de Aprendizaje-SENA regulará, diseñará, normalizará y certificará las competencias laborales”. Este proceso se ha convertido en una importante herramienta para que el sector productivo identifique las brechas de cualificación de los trabajadores y así pueda definir e implementar políticas y estrategias para el desarrollo y gestión del talento humano.
            br
            br
            strong El proceso gestión de certificación de competencias laborales, se diseña desde la Dirección del Sistema Nacional de Formación para el Trabajo - DSNFT y se ejecuta en los Centros de Formación del SENA a nivel nacional.



              
</template>

<script>
export default {
  name: 'Introduccion',
}
</script>

<style lang="scss" scoped></style>
