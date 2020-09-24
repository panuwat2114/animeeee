<template>
  <div>
  <input type="text" v-model="textSearch " />
  <b-button variant="warning" @click="searchData()">Search</b-button><br><br><br><br>
  <!--{{List}}-->
  <b-card-group columns>
  <b-card
  v-for="data in List" :key="data.mal_id"
    :title="data.title"
    :img-src="data.image_url"
    img-alt="Image"
    img-center
    tag="article"
    style="max-width: 20rem;"
    class="mb-2"
  >
    <b-card-text>
    </b-card-text>
    <b-button :href="data.url" variant="danger">READ MORE</b-button>
  </b-card>
  </b-card-group>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      List: null,
      textSearch: "",
    };
  },
  methods: {
    searchData() {
      axios
        .get("https://api.jikan.moe/v3/search/anime?q=" +this.textSearch+"page=5")
        .then((response) => {
          this.List = response.data.results;
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>
<style>
</style>