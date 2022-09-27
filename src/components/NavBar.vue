<template>
  <v-app-bar app color="primary">
    <div class="d-flex align-center">
      <v-img
        alt="Vuetify Logo"
        class="shrink mr-2"
        contain
        src="https://www.freepnglogos.com/uploads/red-logo-png-16.png"
        transition="scale-transition"
        width="50"
      />

      <v-img
        alt="Vuetify Name"
        class="shrink mt-1 hidden-sm-and-down"
        contain
        min-width="100"
        src="https://www.freepnglogos.com/uploads/netflix-logo-text-emblem-31.png"
        width="120"
      />
    </div>

    <v-spacer></v-spacer>
    <v-spacer></v-spacer>
    <v-spacer></v-spacer>
    <div v-for="(link, index) in links" :key="index">
      <v-btn depressed :class="`mr-2 primary  pr-6 pl-6 ${link.class}`">
        <v-icon right dark class="mr-2" large v-if="link.icon">
          {{ link.icon }}
        </v-icon>
        {{ link.btn }}</v-btn
      >
    </div>
    <v-spacer></v-spacer>
    <v-spacer></v-spacer>
    <v-spacer></v-spacer>
    <v-spacer></v-spacer>
    <div>
      <v-btn
        class="mx-2"
        v-if="light"
        fab
        dark
        small
        color="primary--text"
        @click="darkMode()"
      >
        <v-icon dark> mdi-white-balance-sunny </v-icon>
      </v-btn>
      <v-btn
        v-if="night"
        class="mx-2"
        fab
        dark
        small
        color="primary--text"
        @click="darkMode()"
      >
        <v-icon dark> mdi-weather-night </v-icon>
      </v-btn>
    </div>
  </v-app-bar>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
    night: true,
    light: true,
    links: [
      {
        btn: "ORDER ONLINE",
        class: "red--text navbar--text",
        icon: "mdi-fire",
      },
      { btn: "MENU", class: "navbar--text textfontColor--text" },
      { btn: "ABOUT", class: "navbar--text textfontColor--text" },
      { btn: "CONTACT", class: "navbar--text textfontColor--text" },
    ],
  }),
  methods: {
    darkMode() {
      if (this.$vuetify.theme.dark) {
        console.log("dark1");
        this.light = true;
        this.night = false;

        this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
      } else {
        this.night = true;
        this.light = false;
        this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
      }
    },
  },
  created() {
    this.night = false;
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Lato:wght@900&display=swap");

.navbar--text {
  font-family: "Lato", sans-serif;
}
</style>
