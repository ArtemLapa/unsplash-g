<template>
  <div class="main-navigation">
    <v-container>
      <nav class="main-navigation__nav">
        <SearchNavigation/>
        <FiltersNavigation/>
      </nav>
    </v-container>
  </div>
</template>

<script>
import SearchNavigation from "./SearchNavigation";
import FiltersNavigation from "./FiltersNavigation";

export default {
  name: "MainNavigation",
  components: {
    FiltersNavigation,
    SearchNavigation,
  },
};
</script>

<style scoped lang="scss">
$style: "main-navigation";
.#{$style} {
  width: 100%;
  position: relative;
  @include media($screen-desktop) {
    position: absolute;
    bottom: 0;
  }
  @include media($screen-desktop-large) {
    bottom: 10px;
  }
  @include media($screen-fullhd) {
    bottom: 40px;
  }
  @include media($screen-retina) {
    bottom: 80px;
  }
  &__nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-direction: column;
    width: 100%;
    height: auto;
    background: $color-white;
    box-shadow: 0 24px 32px rgba(0, 0, 0, 0.06);
    border: 1px solid $color-gray-mercury;
    border-radius: 8px;
    margin-bottom: 32px;
    padding: 15px 10px;
    @include media($screen-desktop) {
      margin-bottom: 0;
      flex-direction: row;
      height: 80px;
    }
    @include media($screen-desktop-large) {
      padding: 15px 62px;
    }
  }
}
</style>
