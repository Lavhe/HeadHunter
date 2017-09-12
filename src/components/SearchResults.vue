<template>
  <v-ons-page>
    <v-ons-toolbar>
          <div class="left">
            <v-ons-back-button></v-ons-back-button>
          </div>
          <div class="center">{{ txtSearch }}</div>
    </v-ons-toolbar>

    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
  </v-ons-page>
</template>

<script>
export default {
    props:['txtSearch']
}
</script>

<style lang="css">
</style>
