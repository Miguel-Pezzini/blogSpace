<template>
  <div>
    <v-card
    class="mx-auto v-card"
    max-width="344"
  >
  <a :href="source_url" style="text-decoration: none">
    <v-img
      height="200px"
      :src="image_url || 'https://images-assets.nasa.gov/image/PIA22421/PIA22421~thumb.jpg'"
      cover
    ></v-img>
  </a>

    <v-card-title>
      {{ title }}
    </v-card-title>
      <v-card-subtitle>
      {{ description || "No Description" }}
    </v-card-subtitle>
    
    <v-card-actions>
      <v-btn
        color="orange-lighten-2"
        text="Explore"
      ></v-btn>

      <v-spacer style="font-size: 12px; color: #888">{{ pubDate }}</v-spacer>

      <v-btn
        :icon="show ? 'mdi-chevron-up' : 'mdi-chevron-down'"
        @click="show = !show"
      ></v-btn>
    </v-card-actions>

    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>

        <v-card-text>
          {{ content }}
        </v-card-text>
      </div>
    </v-expand-transition>
  </v-card>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
    },
    description: {
      type: String
    },
    content: {
      type: String
    },
    image_url: {
      type: String
    },
    source_url: {
      type: String
    },
    pubDate: {
      type: String
    }
  },
  data() {
    return {
      show: false,
    };
  },
  methods: {
  }
}
</script>

<style scoped>
   .v-card:hover {
    cursor: pointer;
    transition: .4s;
    scale: 1.05;
   }
</style>