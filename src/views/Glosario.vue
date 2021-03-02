<template lang="pug">
.container

  .header-ecored
    h1 Glosario

  .jumbotron.bg-white
    p(v-for="(item,index) of glosarioData" :ref="'glosario-'+item.index")
      strong.mr-2 {{item.termino}}:
      | {{item.significado}}
  
</template>

<script>
import { glosario } from '../config/global'
export default {
  name: 'Glosario',
  data: () => ({
    glosarioData: glosario,
  }),
}
</script>

<style lang="sass" scoped>
p
  &:last-child
    margin-bottom: 0
</style>
