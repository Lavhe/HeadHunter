<style scoped>

.header {
    text-align: center;
}

</style>

<template>

<v-ons-page>
    <v-ons-toolbar class="home-toolbar">
        <div class="left">
            <v-ons-toolbar-button @click="$store.commit('splitter/toggle')">
                <v-ons-icon icon="ion-navicon, material:md-menu"></v-ons-icon>
            </v-ons-toolbar-button>
        </div>
        <div class="center">HeadHunter</div>
    </v-ons-toolbar>

    <v-ons-row>
        <search-panel></search-panel>
    </v-ons-row>

    <v-ons-pull-hook :action="refresh" @changestate="refreshState = $event.state">
        <span v-show="refreshState === 'initial'"> Pull to refresh </span>
        <span v-show="refreshState === 'preaction'"> Refreshing ...</span>
        <span v-show="refreshState === 'action'">
          <v-ons-progress-circular indeterminate></v-ons-progress-circular>
        </span>
    </v-ons-pull-hook>

    <v-ons-row>
        <v-ons-col v-for="n in 10">
            <v-ons-card>
                <img src="https://monaca.io/img/logos/download_image_onsenui_01.png" alt="Onsen UI" style="width: 100%">
                <div class="title">
                    Awesome framework
                </div>
                <div class="content">
                    <div>
                        <v-ons-button>
                            <v-ons-icon icon="ion-thumbsup"></v-ons-icon>
                        </v-ons-button>
                        <v-ons-button>
                            <v-ons-icon icon="ion-share"></v-ons-icon>
                        </v-ons-button>
                    </div>
                    <v-ons-list>
                        <v-ons-list-header>Bindings</v-ons-list-header>
                        <v-ons-list-item>Vue</v-ons-list-item>
                        <v-ons-list-item>Angular</v-ons-list-item>
                        <v-ons-list-item>React</v-ons-list-item>
                    </v-ons-list>
                </div>
            </v-ons-card>
        </v-ons-col>
    </v-ons-row>

</v-ons-page>

</template>

<script>

import SearchPanel from './SearchPanel';

export default {
    name: 'home',
    data() {
        return {
            refreshState : 'initial',
            counter:0
        }
    },
    methods: {
        refresh: function(done) {
            this.$ons.notification.toast('refreshing', {timeout: 2000});
            done();
        }
    },
    mounted: function() {

    },
    components: {
        SearchPanel
    }
}

</script>
