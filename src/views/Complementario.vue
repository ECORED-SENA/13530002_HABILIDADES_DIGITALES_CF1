<template lang="pug">
.container
  .header-ecored
    h1 Material complementario

  .jumbotron.bg-white

    table.table.table-bordered.table-striped
      thead.thead-dark
        tr
          th.text-center Autor, (año del documento o material),  Nombre del documento o material.
          th.text-center Tipo de material ( Video, capítulo de libro, articulo, otro) 
          th.text-center(style="width:150px") Enlace del Recurso o Archivo del documento o material

      tbody
        tr
          td Aprenda Java como si estuviera en primero.
          td PDF
          td 
            a(href="media/documentos/complementarios/MC_AA2_Aprenda_Java.pdf", target="_blank")
            span.fa.fa-download(aria-hidden="true") Descargar     
        tr
          td Fundamentos de Programación en JAVA
          td PDF
          td 
            a(href="media/documentos/complementarios/MC_AA2_Fundamentos_Programacion_Java.pdf", target="_blank") 
            span.fa.fa-download(aria-hidden="true") Descargar                                      
</template>

<script>
export default {
  name: 'Complementario',
}
</script>

<style lang="sass" scoped></style>
