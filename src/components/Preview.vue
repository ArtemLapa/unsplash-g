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
        <img src="../assets/images/preview-image.jpg" alt="Preview image" class="preview__image" />
      </div>
    </div>

    <MainNavigation />
  </section>
</template>

<script>
import MainNavigation from "./Layouts/MainNavigation/MainNavigation";
export default {
  name: "Preview",
  components: { MainNavigation },
};
</script>

<style scoped lang="scss">
$style: "preview";
.#{$style} {
  height: calc(1080px - 108px);
  margin-bottom: 244px;
  box-shadow: inset 0 -2px 0 rgba(0, 0, 0, 0.04);
  position: relative;
  &__wrapper {
    display: flex;
  }
  &__left-side {
    width: 100%;
    max-width: 40.42%;
    display: flex;
    justify-content: center;
    padding-top: 158px;
  }
  &__heading {
    @include h1();
    max-width: 418px;
    margin-bottom: 36px;
  }
  &__description {
    @include text(16px, 300, $color-green-rangoon);
    letter-spacing: -0.2px;
    line-height: 26px;
    text-align: left;
    font-family: $helvetica-light;
    max-width: 330px;
    word-break: normal;
    margin-bottom: 24px;
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
  &__image {
    display: block;
    height: auto;
    width: 100%;
    max-width: 1444px;
  }
}
</style>
