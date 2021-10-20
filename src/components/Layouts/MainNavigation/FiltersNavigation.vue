<template>
  <ul class="filters-navigation__list">
    <li
      class="filters-navigation__item"
      v-for="filter in filters"
      :key="filter.id"
      @click="activeFilter"
      :class="[filter.active ? 'filters-navigation__item--active' : 'filters-navigation__item']"
    >
      {{ filter.value }}
    </li>
  </ul>
</template>

<script>
export default {
  name: "FiltersNavigation",
  data: () => ({
    isActiveFilter: false,
    filters: [
      { id: 0, value: "Trending", active: true },
      { id: 1, value: "Nature", active: false },
      { id: 2, value: "Travel", active: true },
      { id: 3, value: "Animals", active: false },
      { id: 4, value: "Food", active: false },
      { id: 5, value: "Health", active: false },
      { id: 6, value: "Technology", active: false },
      { id: 7, value: "Events", active: false },
    ],
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
  &__list {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 63px 0 38px;
  }
  &__item {
    @include text(16px, 400, $color-grey-santas);
    font-family: $helvetica;
    letter-spacing: -0.2px;
    padding: 11px 24px 10px 23px;
    border: 1px solid $color-gray-athens;
    border-radius: 20px;
    cursor: pointer;
    transition: color 0.2s ease-in, border-color 0.2s ease-in;
    // &:hover {
    //   font-family: $helvetica-medium;
    //   font-weight: 500;
    //   color: $color-gray-mako;
    //   border-color: $color-gray-mako;
    // }
    &:first-child {
      @include text(16px, 500, $color-green-rangoon);
      font-family: $helvetica-medium;
      border: none;
      padding-left: 0;
    }
    &--active {
      font-family: $helvetica-medium;
      font-weight: 500;
      color: $color-gray-mako;
      border-color: $color-gray-mako;
    }
  }
}
</style>
