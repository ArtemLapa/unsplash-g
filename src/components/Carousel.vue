<template>
  <carousel
    :nav="false"
    :dots="false"
  >
    <div
      v-for="thumbnail in thumbnails"
      :key="thumbnail"
      class="gallery-item-wrapper"
    >
      <v-img
        height="112"
        max-width="131"
        :src="thumbnail"
      />
    </div>
  </carousel>
</template>

<script>
import carousel from "vue-owl-carousel";

export default {
  name: "Carousel",
  components: {
    carousel
  },
  props: {
    thumbnails: {
      type: Array,
      default: () => [],
    }
  }
}
</script>

<style lang="scss">
.gallery-item-wrapper {
  .v-image {
    border-radius: 8px;
  }
}

.owl-stage-outer {
  .owl-stage {
    display: flex;
  }

  .owl-item {
    margin-right: 16px;
  }
}
</style>
