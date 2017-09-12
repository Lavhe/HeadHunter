<template>
  <v-ons-page>
    <v-ons-toolbar modifier="transparent"></v-ons-toolbar>

    {{ title }}
    <br />

  </v-ons-page>
</template>

<script>
export default {
  name: 'EmployeeProfile',
  data () {
    return {
       title:''
    }
  },
  methods: {

  },
  mounted:function(){
    this.title = "Employee Name"

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
