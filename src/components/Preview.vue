<template>
  <section class="preview">
    <div class="preview__wrapper">

      <div class="preview__left-side">
        <div class="preview__content">
          <h1 class="preview__heading">
            Photo of the Day by guangxi liu
          </h1>

          <p class="preview__description">
            The internet’s source of freely usable images. Powered by creators everywhere.
          </p>

          <button class="preview__btn">Explore All</button>
        </div>
      </div>

      <div class="preview__right-side">
        <div class="preview__image-wrapper">
          <v-img
            src="../assets/images/preview-image.jpg"
            max-width="1144"
            max-height="980"
            contain
            transition="0"
            alt="Preview image"/>
        </div>
      </div>
    </div>

    <MainNavigation/>
  </section>
</template>

<script>
import MainNavigation from "./Layouts/FilterNavigation/MainNavigation";

export default {
  name: "Preview",
  components: {MainNavigation},
};
</script>

<style scoped lang="scss">
$style: "preview";
.#{$style} {
  //height: calc(1080px - 114px);
  margin-bottom: 50px;
  box-shadow: inset 0 -2px 0 rgba(0, 0, 0, 0.04);
  position: relative;
  @include media($screen-netbook) {
    margin-bottom: 110px;
  }
  @include media($screen-desktop) {
    margin-bottom: 150px;
  }
  @include media($screen-retina) {
    margin-bottom: 244px;
  }

  &__wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 32px;
    @include media($screen-desktop) {
      flex-direction: row;
      align-items: stretch;
    }
  }

  &__left-side {
    width: 80%;
    //padding-top: 98px;
    display: flex;
    justify-content: center;
    order: 2;
    @include media($screen-desktop) {
      width: 100%;
      max-width: 40.72%;
      padding-left: 2%;
    }
    @include media($screen-fullhd) {
      padding-top: 80px;
      order: 1;
    }
    @include media($screen-retina) {
      padding-top: 157px;
      padding-left: 0;
    }
  }

  &__right-side {
    width: 100%;
    max-width: 100%;
    order: 1;
    margin-bottom: 20px;
    @include media($screen-desktop) {
      max-width: 59.28%;
      order: 2;
      margin-bottom: 0;
    }
  }

  &__heading {
    @include h1();
    margin-bottom: 41px;
    @include media($screen-desktop) {
      margin-bottom: 16px;
      max-width: 418px;
      width: 100%;
    }
    @include media($screen-desktop-large) {
      margin-bottom: 41px;
    }
  }

  &__description {
    @include text(16px, 300, $color-green-rangoon);
    letter-spacing: -0.2px;
    line-height: 26px;
    text-align: left;
    font-family: $helvetica-light;
    word-break: normal;
    margin-bottom: 24px;
    @include media($screen-desktop) {
      max-width: 330px;
    }
  }

  &__btn {
    width: 290px;
    height: 72px;
    border-radius: 43px;
    background: $color-green-aqua;
    cursor: pointer;

    @include text(18px, 700, $color-white);
    letter-spacing: -0.22px;
    font-family: $helvetica-bold;
  }

  &__image-wrapper {
    background-color: #71737c;
  }
}
</style>
