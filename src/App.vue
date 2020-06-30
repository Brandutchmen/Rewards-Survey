<template>
  <v-app>
    <v-content>
        <v-img
                max-height="100%"
                width="auto"
                src="background.jpg"
                gradient="to top right, rgba(100,115,201,.33), rgba(0,0,0,.2)"
        >
            <v-row
                    align="center"
                    justify="center"
            >
                <v-card class="mt-16 pb-4 px-4">
                    <v-row>
                    <v-img
                            class=""
                            width="200"
                            src="logo.png"
                    ></v-img>

                    </v-row>
                    <v-col align-self="center" class="text-center">
                    <h1 class="font-weight-medium">Complete this survey to win a $50 Walmart Gift Card!</h1>
                </v-col>
                <HelloWorld/>
            </v-card>
            </v-row>
        </v-img>
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',

  components: {
    HelloWorld,
  },

  data: () => ({
    //
  }),
};
</script>
