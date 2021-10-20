<template>
  <div class="card__cards-wrapper row">
    <div class="card" v-for="post in posts" :key="post.id" :class="[!post.bigCard ? '' : 'card--large']">
      <div class="card__content" :class="[!post.bigCard ? '' : 'card__content--large']">
        <template v-if="!post.bigCard">
          <div>
            <v-img max-height="258" max-width="368" :src="post.screen"></v-img>

            <div class="card__text-content">
              <h4 class="card__author-name">{{ post.author }}</h4>
              <p class="card__location">{{ post.location }}</p>
              <p class="card__description">{{ post.description }}</p>
            </div>
          </div>

          <div class="card__footer">
            <div class="card__left">
              <BookmarkIcon class="card__icon" />
            </div>

            <div class="card__right">
              <div class="card__icon-wrapper">
                <HeartIcon class="card__icon" />
                <span class="card__icon-counter">128</span>
              </div>

              <div class="card__icon-wrapper">
                <MessageIcon class="card__icon" />
                <span class="card__icon-counter">512</span>
              </div>
            </div>
          </div>
        </template>

        <template v-if="post.bigCard">
          <v-img height="501" max-width="368" :src="post.screen" class="card__large-image" />

          <div class="card__large-info">
            <div class="card__text-content">
              <h4 class="card__author-name card__author-name--large">{{ post.author }}</h4>
              <p class="card__location">{{ post.location }}</p>
              <p class="card__description">{{ post.description }}</p>
            </div>

            <div class="card__mini-gallery">
              <v-img
                v-for="thumbnail in post.thumbnails"
                :key="thumbnail"
                height="112"
                max-width="132"
                :src="thumbnail"
              ></v-img>
              <!-- <v-carousel
                    v-model="model"
                    :show-arrows="false"
                  >
                    <v-carousel-item
                      v-for="(srcImg, index) in post['carousel-items']"
                      :key="index"
                    >
                      <v-img
                        height="258"
                        max-width="368"
                        :src="srcImg"
                      ></v-img>
                    </v-carousel-item>
                  </v-carousel> -->
            </div>

            <div class="card__footer">
              <div class="card__left">
                <BookmarkIcon class="card__icon" />
                <ModalWindow />
              </div>

              <div class="card__right">
                <div class="card__icon-wrapper">
                  <HeartIcon class="card__icon" />
                  <span class="card__icon-counter">128</span>
                </div>

                <div class="card__icon-wrapper">
                  <MessageIcon class="card__icon" />
                  <span class="card__icon-counter">512</span>
                </div>
              </div>
            </div>
          </div>
        </template>
      </div>
    </div>
  </div>
</template>

<script>
import HeartIcon from "../../Icons/HeartIcon";
import BookmarkIcon from "../../Icons/BookmarkIcon";
import MessageIcon from "../../Icons/MessageIcon";
import ModalWindow from "../../ModalWindow.vue";

export default {
  name: "MainCard",
  components: {
    MessageIcon,
    BookmarkIcon,
    HeartIcon,
    ModalWindow,
  },
  props: {
    posts: {
      type: Array,
      default: () => [],
    },
  },
  data: () => ({
    model: 0,
    colors: ["primary", "secondary", "yellow darken-2", "red", "orange"],
  }),
};
</script>

<style scoped lang="scss">
$style: "card";
.#{$style} {
  /* Common card style */
  //max-width: 368px;
  //flex-basis: 23.47%;
  max-width: 23.35%;
  height: 501px;
  padding: 0 16px;
  margin-bottom: 32px;
  &--large {
    //max-width: 768px;
    //flex-basis: 48.98%;
    max-width: 46.74%;
  }

  &__cards-wrapper {
    display: flex;
    flex-wrap: wrap;
    margin: 0 -16px;
  }
  &__content {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    border: 1px solid $color-gray-gallery;
    border-radius: 10px;
    height: 100%;
    &--large {
      display: flex;
      flex-direction: row;
    }
  }
  &__text-content {
    padding: 40px 40px 0px 40px;
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
    }
  }
  &__location {
    @include text(12px, normal, $color-gray-alum);
    font-family: $helvetica;
    letter-spacing: -0.15px;
    line-height: 16px;
    margin-bottom: 17px;
  }
  &__description {
    @include text(13px, 400, $color-grey-oslo);
    font-family: $helvetica;
    letter-spacing: -0.16px;
    line-height: 18px;
    text-align: left;
  }
  &__footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 48px;
    padding: 0 40px;
    border-top: 1px solid $color-gray-gallery;
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

  /* Large card style */
  &__large-image {
    object-fit: scale-down;
  }
  &__large-info {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  &__mini-gallery {
    display: flex;
  }
}
</style>
