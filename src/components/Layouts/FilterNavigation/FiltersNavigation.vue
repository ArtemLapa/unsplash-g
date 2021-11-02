<template>
  <div class="filters-navigation">
    <v-chip-group
      class="filters-navigation__list"
      multiple
      :show-arrows="false"
      mobile-breakpoint="961"
    >
      <v-chip
        class="filters-navigation__item"
        active-class="filters-navigation__item--active"
        v-for="tag in filters"
        :key="tag.id"
      >
        {{ tag.value }}
      </v-chip>
    </v-chip-group>
  </div>
</template>

<script>
export default {
  name: "FiltersNavigation",
  data: () => ({
    isActiveFilter: false,
    filters: [
      {id: 0, value: "Trending", active: true},
      {id: 1, value: "Nature", active: false},
      {id: 2, value: "Travel", active: true},
      {id: 3, value: "Animals", active: false},
      {id: 4, value: "Food", active: false},
      {id: 5, value: "Health", active: false},
      {id: 6, value: "Technology", active: false},
      {id: 7, value: "Events", active: false},
    ],
    model: null,
  }),
  methods: {
    activeFilter() {
      return (this.filters.active = !this.filters.active);
    },
  },
};
</script>

<style scoped lang="scss">
$style: "filters-navigation";
.#{$style} {
  max-width: 80%;
  @include media($screen-desktop) {
    max-width: 60%;
  }

  &__list {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0;
    position: relative;
    //padding: 0 63px 0 38px;
  }

  &__item {
    @include text(16px, 400, $color-grey-santas);
    font-family: $helvetica-medium;
    letter-spacing: -0.2px;
    display: inline-flex;
    justify-content: center;
    align-items: center;
    transition: color 0.2s ease-in, border-color 0.2s ease-in;
    border: 1px solid $color-gray-athens;

    &.theme--light.v-chip:not(.v-chip--active) {
      background: $color-white;
    }

    &.v-chip {
      height: 40px;
      border-radius: 20px;
      width: 103px;
      margin: 0 0 0 8px;
      padding: 0;
      color: $color-grey-santas;

      &:first-child {
        @include text(16px, 500, $color-green-rangoon);
        border: none;
        margin: 0;
      }
    }

    &--active {
      &.v-chip {
        font-weight: 500;
        color: $color-gray-mako;
        border-color: $color-gray-mako;

        &:before {
          opacity: 0;
        }
      }
    }
  }
}
</style>
