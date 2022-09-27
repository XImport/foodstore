<template>
  <v-container>
    <v-carousel
      v-model="model"
      hide-delimiter-background
      touch
      show-arrows-on-hover
    >
      <v-carousel-item v-for="(item, i) in items" :key="i">
        <v-img
          :src="item.src"
          containclass="d-block mx-auto"
          max-width="100%"
          max-height="100%"
        ></v-img>
      </v-carousel-item>
    </v-carousel>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    model: 0,
    items: [
      {
        src: "https://images3.alphacoders.com/104/1048292.jpg",
      },
      {
        src: "https://wallpapersmug.com/download/3840x2400/ebde76/delicious-pizza-food.jpg",
      },

      {
        src: "https://rare-gallery.com/mocahbig/28301-ChopsticksAsian-HD-Wallpaper.jpg",
      },
    ],
  }),
};
</script>
<style>
.img-carousel {
  background-size: cover !important;
  margin: auto !important;
  display: block !important;
  height: auto !important;
  max-width: 100% !important;
}
</style>
