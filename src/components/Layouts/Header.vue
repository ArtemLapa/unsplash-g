<template>
  <header class="header">
    <div class="my-container">
      <nav class="header__navigation">
        <ul class="header__navigation-list">
          <li class="header__navigation-item">
            <router-link to="/" class="header__navigation-link" exact-active-class="header__active-link">
              Home
            </router-link>
          </li>
          <li class="header__navigation-item">
            <router-link
              to="/featured-collections"
              class="header__navigation-link"
              exact-active-class="header__active-link"
            >
              Featured collections
            </router-link>
          </li>
          <li class="header__navigation-item">
            <router-link to="/profile" class="header__navigation-link" exact-active-class="header__active-link">
              My profile
            </router-link>
          </li>
        </ul>

        <div class="header__icons-group">
          <UserIcon name="user-icon" />
          <SearchIcon name="search-icon" />
        </div>
      </nav>
    </div>
  </header>
</template>

<script>
import UserIcon from "../Icons/UserIcon";
import SearchIcon from "../Icons/SearchIcon";
export default {
  name: "Header",
  components: { SearchIcon, UserIcon },
};
</script>

<style scoped lang="scss">
$style: "header";
.#{$style} {
  height: 100px;
  display: flex;
  align-items: center;
  background: $color-white;
  box-shadow: 0 2px 69px rgba(0, 0, 0, 0.11);
  &__navigation {
    display: flex;
    align-items: center;
    justify-content: flex-end;
  }
  &__navigation-list {
    display: flex;
    width: 100%;
    max-width: 324px;
    justify-content: space-between;
    margin-right: 60px;
  }
  /*&__navigation-item {
    font-size: 16px;
    line-height: 16px;
  }*/
  &__navigation-link {
    @include text(13px, 500, $color-gray-shark);
    font-family: $helvetica-medium;
  }
  &__active-link {
    color: $color-green-aqua;
    font-family: $helvetica-bold;
    font-weight: 700;
  }
  &__icons-group {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    max-width: 68px;
  }
}
</style>
