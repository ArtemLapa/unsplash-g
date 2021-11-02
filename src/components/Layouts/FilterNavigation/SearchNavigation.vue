<template>
  <form class="search-navigation" v-on:submit.prevent>
    <input
      class="search-navigation__input"
      type="search"
      name="search"
      placeholder="Search for high-resolution photos"
    />
    <button type="submit">
      <v-icon color="black" size="25">
        mdi-magnify
      </v-icon>
    </button>
  </form>
</template>

<script>

export default {
  name: "SearchNavigation",
}
</script>

<style scoped lang="scss">
$style: "search-navigation";
.#{$style} {
  display: flex;
  align-items: center;
  width: 100%;
  max-width: 80%;
  height: 100%;
  position: relative;
  margin-bottom: 24px;
  @include media($screen-desktop) {
    margin-bottom: 0;
    max-width: 35%;
  }

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
    width: 100%;
    border: none;
    outline: none;
    @include text(16px, 300, $color-grey-storm);
    letter-spacing: -0.2px;
    font-family: $helvetica-light;
    &:focus {
      outline: 0;
      border-bottom: 1px solid #03a9f4;
      box-shadow: none;
      color: $color-green-rangoon;
    }
  }

}
</style>
