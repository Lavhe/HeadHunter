<style scoped>
ons-splitter-side[side=left][animation=overlay] {
  border-right: 1px solid #BBB;
}
</style>

<template>
<v-ons-page id="app">
  <v-ons-splitter>
    <v-ons-splitter-side swipeable collapse width="250px" :animation="$ons.platform.isAndroid() ? 'overlay' : 'reveal'" :open.sync="menuIsOpen">
    </v-ons-splitter-side>
    <fab-button></fab-button>
    <v-ons-splitter-content>
      <home-page></home-page>
    </v-ons-splitter-content>
  </v-ons-splitter>
</v-ons-page>
</template>

<script>
import HomePage from './components/HomePage'
import FabButton from './components/FabButton'
import EmployeeProfile from './components/EmployeeProfile'
import EmployerProfile from './components/EmployerProfile'

export default {
  name: 'app',
  computed: {
    menuIsOpen: {
      get() {
        return this.$store.state.splitter.open
      },
      set(newValue) {
        this.$store.commit('splitter/toggle', newValue)
      }
    }
  },
  components: {
    HomePage,
    FabButton,
    EmployerProfile,
    EmployeeProfile
  }
}
</script>
