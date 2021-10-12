<template>
  <form class="search-navigation">
    <input
        class="search-navigation__input"
        type="search"
        placeholder="Search for high-resolution photos"
        @focusin="moveSearch"
        @focusout="moveSearch"
    >
    <SearchIcon
        class="search-navigation__icon"
        :class="[isMove ? 'search-navigation__icon--move' : 'search-navigation__icon']"
    />
  </form>
</template>

<script>
import SearchIcon from "../../Icons/SearchIcon";
export default {
  name: "SearchNavigation",
  components: {
    SearchIcon,
  },
  data: () => ({
    isMove: false
  }),
  methods: {
    moveSearch() {
      return  this.isMove = !this.isMove
    }
  }
}
</script>

<style scoped lang="scss">
$style: "search-navigation";
.#{$style} {
  width: 100%;
  max-width: 600px;
  height: 100%;
  position: relative;
  &__icon {
    position: absolute;
    top: 50%;
    right: 10%;
    transform: translate(-10%, -50%);
    transition: right .2s ease-out;
    &--move {
      right: 0;
      transform: translate(0, -50%);
    }
  }
  &__input {
    border-radius: 8px;
    height: 100%;
    width: 100%;
    border: none;
    outline: none;
    padding: 0 62px 0 64px;
    @include text(16px, 300, $color-grey-storm);
    letter-spacing: -0.2px;
    font-family: $helvetica-light;
  }

}
</style>