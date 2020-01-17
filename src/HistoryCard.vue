<template>
  <div @mouseenter="showOptions" @mouseleave="showOptions">
    <b-card
      :title="
        img.landmark != 'Cant identify landmark'
          ? img.landmark.landmarkName
          : 'Not a landmark'
      "
      :img-src="img.url"
      img-alt="Image"
      img-top
      tag="article"
      style="max-width: 20rem;"
      class="my-2"
      border-variant="secondary"
    >
      <div v-show="activeOptions">
        <b-card-text>
          <!-- <h3>{{ img.landmark.landmarkName }}</h3> -->
          <p>Location :</p>
          <ul>
            <li>latitude: {{ img.landmark.location.latitude }}</li>
            <li>longitude: {{ img.landmark.location.longitude }}</li>
          </ul>
          <p>Score : {{ img.landmark.score }}</p>
        </b-card-text>

        <share-button></share-button>
      </div>
    </b-card>
  </div>
</template>

<script>
import ShareButton from "./ShareButton.vue";

export default {
  props: ["img"],
  data() {
    return {
      activeOptions: false
    };
  },
  methods: {
    showOptions() {
      this.activeOptions = !this.activeOptions;
    }
  },
  components: {
    ShareButton
  }
};
</script>

<style scoped>
.upload-history:hover {
  background-color: red;
}
</style>
