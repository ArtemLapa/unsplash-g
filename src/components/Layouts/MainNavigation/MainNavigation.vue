<template>
  <div class="main-navigation">
    <div class="container">
      <nav class="main-navigation__nav">
        <SearchNavigation />
        <FiltersNavigation/>
      </nav>
    </div>
  </div>

</template>

<script>
import SearchNavigation from "./SearchNavigation";
import FiltersNavigation from "./FiltersNavigation";
export default {
  name: "MainNavigation",
  components: {
    FiltersNavigation,
    SearchNavigation
  }
}
</script>

<style scoped lang="scss">
$style: "main-navigation";
.#{$style} {
  width: 100%;
  position: absolute;
  bottom: 80px;
  z-index: 5;
  &__nav {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    height: 80px;
    background: $color-white;
    box-shadow: 0 24px 32px rgba(0, 0, 0, 0.06);
    border: 1px solid $color-gray-mercury;
    border-radius: 8px;
  }
}

</style>