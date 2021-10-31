<template>
  <v-app>
    <v-app-bar
      app
      dark
    >
      <div class="d-flex align-center">
        <h1>vue-some-functions</h1>
      </div>

      <v-spacer></v-spacer>

      <v-switch
        v-model="darkMode"
        inset
        color="primary"
        hide-details
        class="mr-6"
      >
        <template v-slot:label>
          <span class="font-italic">
            {{!darkMode ? 'Light' : 'Dark'}}
          </span>
        </template>
      </v-switch>

    </v-app-bar>

    <v-main>
      <HelloWorld/>
    </v-main>

    <ScrollTop/>

  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import ScrollTop from './components/ScrollTop';

export default {
  name: 'App',

  components: {
    HelloWorld,
    ScrollTop
  },

  data: () => ({
    darkMode: false,
  }),

  watch: {
    darkMode() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
    }
  }
};
</script>
