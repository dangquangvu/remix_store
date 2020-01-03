<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
      <div class="text-center">
        <logo />
        <vuetify-logo />
      </div>
      <p class="demo">4234234</p>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quasi eaque iure voluptatibus. Tenetur fugit earum voluptatem id, omnis non dolorum, ipsa commodi libero illo voluptas. Hic facere rerum quasi ipsam?</p>
    </v-flex>
  </v-layout>
</template>
<style lang="css" scoped>
  @import url('~/assets/css/main.css');
</style>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo
  }
}
</script>
