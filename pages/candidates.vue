<template>
  <div>
    <header-component></header-component>
    <candidates-component></candidates-component>
    <button-add-component></button-add-component>
  </div>
</template>
<script>
  import { HeaderComponent } from '~/components/common/layout'
  import { CandidatesComponent } from '~/components/common/post'
  import ButtonAddComponent from '~/components/common/buttons/ButtonAddComponent'
  export default {
    data () {
      return {}
    },
    components: {
      HeaderComponent,
      CandidatesComponent,
      ButtonAddComponent
    }
  }
</script>
<style lang="scss">
</style>
