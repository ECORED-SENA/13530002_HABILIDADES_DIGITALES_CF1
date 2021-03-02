<template lang="pug">
footer
  #Creditos.footer
    .container

      h1 Créditos               
      .brand-line-primary

      .row
        .col-12.col-md-5
          h3.footer-subtitulo.mb-4 ECOSISTEMA DE RECURSOS EDUCATIVOS DIGITALES 

          p.footer-texto.mb-2
            strong Maria Camila Garcia Santamaria
            br   
            span.text-small Líder del equipo
            br
            span.text-small Dirección general

      .row.mt-5
        .col-12.col-md-6
          h4.footer-subtitulo-2.mt-0
            .fa.fa-caret-right.mr-2
            | Contenido Instruccional

          p.footer-texto
            strong Rafael Neftalí Lizcano Reyes
            br
            span.text-small Asesor metodológico y pedagógico
            br
            span.text-small.text-uppercase Centro Industrial Del Diseño Y La Manufactura
            br
            span.text-small Regional Santander

          p.footer-texto
            strong Tania Yaneth Ramírez Benítez
            br               
            span.text-small Soporte organizacional
            br
            span.text-small.text-uppercase CENTRO DE COMERCIO Y SERVICIOS 
            br
            span.text-small Regional Tolima

          p.footer-texto
            strong Jhonaimer Diaz Cerquera
            br
            span.text-small Experto temático
            br
            span.text-small.text-uppercase Centro de desarrollo Agroempresarial y turístico
            br
            span.text-small Regional Huila

          p.footer-texto
            strong Miguel Ricardo Rivera Lizcano
            br
            span.text-small Experto temático
            br
            span.text-small Dirección general

          p.footer-texto
            strong Andrés Felipe Velandia Espitia
            br   
            span.text-small Diseñador Instruccional 
            br
            span.text-small.text-uppercase Centro de Diseño y Metrología
            br
            span.text-small Regional Distrito Capital

          p.footer-texto
            strong Vilma Lucía Perilla Méndez
            br   
            span.text-small Evaluador instruccional
            br
            span.text-small.text-uppercase Centro de Gestión Industrial
            br
            span.text-small Regional Distrito Capital

          p.footer-texto
            strong Julieth Paola Vital López
            br   
            span.text-small Revisora de estilo
            br
            span.text-small.text-uppercase Centro para la Industria y la Comunicación Gráfica
            br
            span.text-small Regional Distrito Capital
                
        .col-12.col-md-6
          h4.footer-subtitulo-2.mt-0 
            .fa.fa-caret-right.mr-2
            | Diseño y desarrollo de recursos educativos digitales
          
          p.footer-texto
            strong Francisco José Lizcano Reyes 
            br   
            span.text-small Responsable equipo
            br
            span.text-small.text-uppercase Centro Industrial Del Diseño Y La Manufactura
            br
            span.text-small Regional Santander

          p.footer-texto
            strong Leyson Fabian Castaño Perez
            br   
            span.text-small Integración de recursos y pruebas
            br
            span.text-small.text-uppercase CENTRO DE COMERCIO Y SERVICIOS
            br
            span.text-small Regional Tolima

          p.footer-texto                           
            strong Oleg Litvin
            br  
            strong Wilson Andres Arenales Cáceres
            br
            span.text-small Diseño Web & Producción Audiovisual
            br
            span.text-small.text-uppercase Centro Industrial Del Diseño Y La Manufactura
            br
            span.text-small Regional Santander

          p.footer-texto
            strong Andres Mauricio Santaella Ochoa
            br
            span Desarrollo front-end
            br                
            span.text-small.text-uppercase Centro Industrial Del Diseño Y La Manufactura
            br
            span.text-small Regional Santander

          h4.footer-subtitulo-2.mt-5
            .fa.fa-caret-right.mr-2
            | Gestores de repositorio

          p.footer-texto
            strong Ricardo Alfonso Gonzalez Vargas
            br
            span Validación de recursos
            br
            span.text-small CENTRO DE COMERCIO Y SERVICIOS
            br
            span Regional Tolima

      .row.justify-content-center.align-items-center.mt-5
        img(src="@/assets/images/logos/senaLogo.svg", style="max-width:100px")

  section#cc
    .container
      .d-flex.flex-column.flex-sm-row
        span.pr-3
          i.icon.cc

        span
          | Este material puede ser distribuido, copiado y exhibido por terceros si se muestra en los créditos. No se puede obtener ningún beneficio comercial y las obras derivadas tienen que estar bajo los mismos términos de la licencia que
          | el trabajo original.

</template>

<script>
export default {
  name: 'Creditos',
}
</script>

<style lang="scss" scoped></style>
