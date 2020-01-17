<template>
  <div>
    <a
      class="twitter-share-button"
      :href="
        `https://twitter.com/intent/tweet?text=${img.landmark.landmarkName}&url=${img.url}`
      "
      data-size="large"
    >
      Tweet
    </a>
    </div>
  </div>
</template>

<script>
export default {
  props: ["img"],
  data() {
    return {};
  }
};
</script>

<style scoped></style>
