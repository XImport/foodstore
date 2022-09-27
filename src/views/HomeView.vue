<template>
  <div>
    <NavBar />
    <SubNav />
    <div class="text-center pa-6">
      <h1>delivered to your door !</h1>
    </div>

    <v-container fill-height id="container-center">
      <v-row align="center" justify="center">
        <v-col v-for="(card, index) in Cards" :key="index" cols="12" sm="4">
          <v-card class="pa-2" outlined tile id="card--custom">
            <v-spacer></v-spacer>
            <v-img class="img--card" :src="card.img"></v-img>
            <v-spacer></v-spacer>
            <v-card-title class="justify-center">{{ card.title }}</v-card-title>
            <p class="text-center">
              {{ card.paragraph }}
            </p>
            <v-card-actions class="justify-center">
              <router-link to="#" class="red--text"
                ><v-icon class="red--text">{{ card.icon }}</v-icon>
                <strong>
                  {{ card.link }}
                </strong>
              </router-link>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
      <div>
        <h1>hello world</h1>
      </div>
    </v-container>
  </div>
</template>

<script>
import NavBar from "@/components/NavBar.vue";

import SubNav from "@/components/SubNavBar.vue";

export default {
  name: "HomeView",
  data() {
    return {
      Cards: [
        {
          title: "Become a Dasher",
          paragraph:
            "As a delivery driver, you'll make reliable money—working anytime, anywhere.",
          link: "Start earning",
          img: "https://cdn.doordash.com/media/consumer/home/landing/new/ScootScoot.svg",
          icon: "mdi-arrow-right",
        },
        {
          title: "Become a Become a Partner",
          paragraph:
            "Grow your business and reach new customers by partnering with us.",
          link: "Sign up Your Store",
          img: "https://cdn.doordash.com/media/consumer/home/landing/new/Storefront.svg",
          icon: "mdi-arrow-right",
        },
        {
          title: "Try The App",
          paragraph:
            "Experience the best your neighborhood has to offer, all in one app.",
          link: "Get The App",
          img: "https://cdn.doordash.com/media/consumer/home/landing/new/iphone.svg",
          icon: "mdi-arrow-right",
        },
      ],
    };
  },
  components: {
    NavBar,
    SubNav,
  },
};
</script>

<style scoped>
#container-center {
  border: 0px solid white;
}

.img--card {
  height: 154px;
  width: 154px;
  margin-left: 25%;
}

#card--custom {
  border: none;
}

a {
  text-decoration: none;
}
</style>
