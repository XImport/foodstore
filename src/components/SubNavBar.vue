<template>
  <div>
    <v-app-bar dense dark color="red">
      <v-app-bar-nav-icon
        class="d-none d-md-flex d-lg-none"
      ></v-app-bar-nav-icon>
      <v-toolbar-title>CATEGORIES</v-toolbar-title>

      <v-spacer></v-spacer>
      <div v-for="(link, index) in links" :key="index">
        <v-btn class="ml-2 red"> {{ link.text }} </v-btn>
      </div>
      <v-spacer></v-spacer>
    </v-app-bar>

    <div class="d-flex pa-2" outlined tile>
      <v-navigation-drawer class="primary hidden-md-and-down" permanent>
        <v-list rounded>
          <v-subheader>CATEGORIES LIST</v-subheader>
          <v-list-item-group v-model="selectedItem" color="red">
            <v-list-item v-for="(item, i) in items" :key="i">
              <v-list-item-icon>
                <v-icon v-text="item.icon"></v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title v-text="item.title"></v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </v-navigation-drawer>

      <v-container>
        <SliderVueVue />
      </v-container>
    </div>
  </div>
</template>

<script>
import SliderVueVue from "@/components/SliderVue.vue";
export default {
  components: { SliderVueVue },
  data() {
    return {
      links: [
        { text: "#pizza" },
        { text: "#Tacos" },
        { text: "#couscous" },
        { text: "#harira" },
        { text: "#Healthy" },
      ],
      rules: [
        (value) => !!value || "Required.",
        (value) => (value && value.length >= 3) || "Min 3 characters",
      ],
      items: [
        { title: "Fruits", icon: "mdi-fruit-cherries" },
        { title: "Grains", icon: "mdi-graph" },
        { title: "Vegetables", icon: "mdi-egg-easter" },
        { title: "Protein", icon: "mdi-weight-lifter" },
        { title: "Yogurt", icon: "mdi-water" },
        { title: "Pasta", icon: "mdi-pizza" },
        { title: "Meals", icon: "mdi-silverware-fork-knife" },
      ],
    };
  },
};
</script>

<style scoped>
.container {
  max-width: 90%;
  max-height: 100%;
}

#secondbar {
  padding: 40px;
}

.v-btn {
  box-shadow: none;
  transition: all 0.4 ease-out;
}
</style>
