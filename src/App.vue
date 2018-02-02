<template>
  <v-app id="app" light>

    <v-navigation-drawer
            clipped
            fixed
            v-model="drawer"
            app
    >
    </v-navigation-drawer>


    <v-toolbar app fixed clipped-left>
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title>Title</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-side-icon class="hidden-md-and-up"></v-toolbar-side-icon>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat>Szukaj <v-icon right>search</v-icon></v-btn>
        <v-btn flat>Kontakt <v-icon right>mail</v-icon></v-btn>
      </v-toolbar-items>
    </v-toolbar>

    <v-content>

      <v-container fluid fill-height>

        <v-layout justify-center align-center>

          <exchange-table></exchange-table>

        </v-layout>

      </v-container>

    </v-content>

    <v-footer fixed>
      <span>&copy; 2018</span>
    </v-footer>
  </v-app>
</template>


<script>

    import ExchangeTable from './components/ExchangeTable.vue';

    export default {

        data(){
            return {
                drawer: null
            }
        },
        props: {
            source: String
        },
        components:{
            ExchangeTable
        }
    }
</script>
