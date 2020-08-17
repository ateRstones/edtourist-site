<template>
    <v-app>
        <v-app-bar
            app
            color="primary"
            dark
        >
            <div class="d-flex align-center">
                <v-img
                    alt="Vuetify Logo"
                    class="shrink mr-2"
                    contain
                    src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
                    transition="scale-transition"
                    width="40"
                />

                <v-img
                    alt="Vuetify Name"
                    class="shrink mt-1 hidden-sm-and-down"
                    contain
                    min-width="100"
                    src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
                    width="100"
                />
            </div>

            <v-spacer></v-spacer>

            <v-btn
                href="https://github.com/vuetifyjs/vuetify/releases/latest"
                target="_blank"
                text
            >
                <span class="mr-2">Latest Release</span>
                <v-icon>mdi-open-in-new</v-icon>
            </v-btn>
        </v-app-bar>

        <v-main>
              <v-container fluid>
                <v-row>
                <v-col cols="12">
                    <v-row
                    :align="alignment"
                    :justify="justify"
                    class="grey lighten-5"
                    style="height: 600px;"
                    >
                    <div
                        v-for="n in 16"
                        :key="n"
                        class="ma-3 pa-6"
                        tile
                    >
                        
            <InfoCard :number="n" />
                    </div>
                    </v-row>
                </v-col>
                <v-col cols="12">
                    <v-row justify="center">
                    <v-col
                        cols="6"
                        md="2"
                    >
                        <v-select
                        v-model="alignment"
                        :items="alignmentsAvailable"
                        label="Align"
                        ></v-select>
                    </v-col>

                    <v-col
                        cols="6"
                        md="2"
                    >
                        <v-select
                        v-model="justify"
                        :items="justifyAvailable"
                        label="Justify"
                        ></v-select>
                    </v-col>
                    </v-row>
                </v-col>
                </v-row>
            </v-container>
        </v-main>
    </v-app>
</template>

<script>
//import HelloWorld from './components/HelloWorld';
import InfoCard from './components/InfoCard';

export default {
    name: 'App',

    components: {
        //HelloWorld,
        InfoCard,
    },

    data: () => ({
        alignmentsAvailable: [
          'start',
          'center',
          'end',
          'baseline',
          'stretch',
        ],
        alignment: 'center',
        dense: false,
        justifyAvailable: [
          'start',
          'center',
          'end',
          'space-around',
          'space-between',
        ],
        justify: 'center',
      }
    ),
};
</script>
