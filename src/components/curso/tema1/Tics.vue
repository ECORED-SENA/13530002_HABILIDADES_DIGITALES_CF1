<template lang="pug">
.tics
  .row.align-items-center.justify-content-center
    .col-8.col-md-5
      img(:src="ticsData[selected].img")
    .col-md-7.d-flex.flex-column.justify-content-between
      IndicadorInteraccion(v-if="showIndicador")
      .tics__btn.h3.mb-0(
        v-for="(item, index) of ticsData",
        :ref="'tics-'+index",
        v-html="item.text"
        :class="{'tics__btn--selected': index === selected }"
        @mouseover="selected = index; showIndicador = false"
      )
</template>

<script>
import IndicadorInteraccion from '../../IndicadorInteraccion'
export default {
  name: 'Tics',
  components: {
    IndicadorInteraccion,
  },
  data: () => ({
    showIndicador: true,
    selected: 0,
    ticsData: [
      {
        img: require('@/assets/images/pages/tema1/img-17.png'),
        text: 'Hablar por <strong>celular</strong>',
      },
      {
        img: require('@/assets/images/pages/tema1/img-18.png'),
        text: 'Revisar el <strong>correo electrónico</strong>',
      },
      {
        img: require('@/assets/images/pages/tema1/img-21.png'),
        text:
          '<strong>Revisar la red social </strong>en la que estamos inscritos',
      },
      {
        img: require('@/assets/images/pages/tema1/img-20.png'),
        text: '<strong>Chatear</strong> con algún amigo',
      },
      {
        img: require('@/assets/images/pages/tema1/img-19.png'),
        text: 'Escribir la <strong>lista de tareas </strong>pendientes',
      },
    ],
  }),
}
</script>

<style lang="sass" scoped>
.tics__btn
  border: 1px solid #5FA6EC
  width: fit-content
  padding: 10px
  border-radius: 15px
  margin: 10px 0
  cursor: pointer

  &--selected
    background-color: #5FA6EC
    color: #fff
</style>
