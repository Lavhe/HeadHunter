<style lang="css">

.center {
    text-align: center;
    margin: auto;
}

</style>

<template>

<v-ons-fab position="bottom right"
           :visible="true"
           ripple="true">
    <v-ons-icon :icon="fabIcon"></v-ons-icon>
</v-ons-fab>

</template>

<script>

export default {
    name: "fab",
    data() {
        return {
            fabLink: '',
            fabIcon:'md-face'
        }
    },
    methods: {

    }
}

</script>
