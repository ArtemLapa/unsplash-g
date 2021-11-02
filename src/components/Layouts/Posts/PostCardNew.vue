<template>
  <v-row>
    <v-col
      lg="3"
      md="4"
      sm="6"
      v-for="post in posts"
      :key="post.id"
    >
      <v-card
        height="501"
        class="card"
        elevation="0"
      >
        <div class="card__content-wrapper">

          <div class="card__header">
            <PostDialog/>

            <div class="card__text-wrapper">
              <h4 class="card__author-name">{{ post.author }}</h4>

              <p class="card__location">{{ post.location }}</p>
              <p class="card__description">{{ post.description }}</p>
            </div>
          </div>

          <div class="card__footer">
            <div class="card__left">
              <BookmarkIcon class="card__icon"/>
            </div>

            <div class="card__right">
              <div class="card__icon-wrapper">
                <HeartIcon class="card__icon"/>
                <span class="card__icon-counter">128</span>
              </div>

              <div class="card__icon-wrapper">
                <MessageIcon class="card__icon"/>
                <span class="card__icon-counter">512</span>
              </div>
            </div>
          </div>
        </div>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import MessageIcon from "@/components/Icons/MessageIcon";
import BookmarkIcon from "@/components/Icons/BookmarkIcon";
import HeartIcon from "@/components/Icons/HeartIcon";
import PostDialog from "@/components/Layouts/Posts/PostDialog";
// import Carousel from "@/components/Carousel";

export default {
  name: "VuetifyCard",
  components: {
    PostDialog,
    // Carousel,
    MessageIcon,
    BookmarkIcon,
    HeartIcon,
  },
  data: () => ({
    // selection: 1,
    model: 0,
  }),
  props: {
    posts: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style lang="scss" scoped>
$style: "card";
.#{$style} {
  width: 100%;
  border: 1px solid $color-gray-gallery;
  border-radius: 8px;

  @include media($screen-retina) {
    max-width: 368px;
    &--large {
      max-width: 768px;
    }
  }

  &__content-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 100%;
    transition: box-shadow .2s ease-in-out;

    &:hover {
      box-shadow: rgb(0 0 0 / 11%) 0px 2px 69px 0px;
    }

    &--large {
      display: flex;
      flex-direction: row;
      justify-content: stretch;
    }
  }

  &__text-wrapper {
    padding: 20px 20px 0 20px;
    @include media($screen-tablet) {
      padding: 40px 40px 0 40px;
    }
  }

  &__author-name {
    @include text(18px, 500, $color-green-rangoon);
    font-family: $helvetica-medium;
    font-style: normal;
    letter-spacing: -0.22px;
    margin-bottom: 6px;

    &--large {
      font-size: 32px;
      letter-spacing: -0.4px;
      line-height: normal;
      margin-bottom: 3px;
    }
  }

  &__location {
    @include text(12px, normal, $color-gray-alum);
    font-family: $helvetica;
    letter-spacing: -0.15px;
    line-height: 16px;
    margin-bottom: 17px;

    &--large {
      line-height: 1.33;
      font-stretch: normal;
      font-style: normal;
    }
  }

  &__description {
    @include text(13px, normal, $color-grey-oslo);
    font-family: $helvetica;
    letter-spacing: -0.16px;
    line-height: 1.38;
    text-align: left;
    margin: 0;
  }

  &__footer {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 48px;
    border-top: 1px solid $color-gray-gallery;
    padding: 0 20px;
    @include media($screen-tablet) {
      padding: 0 40px;
    }
  }

  &__right {
    display: flex;
    align-items: center;
  }

  &__icon-wrapper {
    display: flex;
    align-items: center;

    &:last-child {
      margin-left: 33px;
    }
  }

  &__icon {
    cursor: pointer;
    vertical-align: middle;
  }

  &__icon-counter {
    @include text(14px, 300, $color-gray-alum);
    font-family: $helvetica-light;
    letter-spacing: -0.16px;
    margin-left: 8px;
  }

  /* Large card */
  &__left-side {
    width: 50%;
  }

  &__right-side {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    overflow: hidden;
  }

  &__mini-gallery {
    max-width: 400px;
  }

}
</style>
