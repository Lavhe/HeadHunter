<style lang="css">
  .center{
    text-align:center;
    margin :auto;
  }


</style>

<template>

<v-ons-col vertical-align="center" width="100%">
    <v-ons-row class="center">
        <v-ons-col class="center">
            <p>
                <v-ons-search-input v-on:keyup.enter="performSearch" v-model="txtSearch" placeholder="Search something"></v-ons-search-input>
            </p>
        </v-ons-col>
    </v-ons-row>
    <v-ons-row class="center">
        <v-ons-col class="center">
            <v-ons-button ripple="true" modifier="material--flat" v-on:click="performSearch" style="margin: 6px 0">Search</v-ons-button>
        </v-ons-col>
    </v-ons-row>

</v-ons-col>

</template>

<script>
import SearchResults from './SearchResults'

export default {
    name: "search",
    data() {
        return {
            txtSearch: ''
        }
    },
    methods: {
        performSearch: function() {
            if (!this.txtSearch) {
                this.$ons.notification.toast("Enter a valid search phrase", {
                    timeout: 2000
                });
            } else {
                this.$ons.notification.toast(this.txtSearch, {
                    timeout: 2000
                });

                this.$emit('push-page', { template:'SearchResults'});
            }
        }
    },
    components:{
      App:SearchResults
    }
}

</script>
