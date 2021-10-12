<template>
  <div class="card__cards-wrapper row">

    <div
        class="card"
        v-for="post in posts"
        :key="post.id"
        :class="[!post.bigCard ? '' : 'card--large',]"
    >
      <template v-if="!post.bigCard">
        <v-img height="258" max-width="368" :src="post.screen"></v-img>

        <div class="card__text-content">
          <h4 class="card__author-name">{{post.author}}</h4>
          <p class="card__location">{{post.location}}</p>
          <p class="card__description">{{post.description}}</p>
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

        <v-img height="501" max-width="368" :src="post.screen"></v-img>

        <div class="card__large-content">
          <div class="card__text-content">
            <h4 class="card__author-name card__author-name--large">{{post.author}}</h4>
            <p class="card__location">{{post.location}}</p>
            <p class="card__description">{{post.description}}</p>
          </div>

          <div class="card__mini-gallery">
            <v-carousel
              v-model="model"
              :show-arrows="false"
            >
              <!-- <v-carousel-item
                v-for="(srcImg, index) in post['carousel-items']"
                :key="index"
              >
                <v-img
                  height="258"
                  max-width="368"
                  :src="srcImg"
                ></v-img>
              </v-carousel-item> -->
            </v-carousel>
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
        </div>
      </template>

    </div>
  </div>
</template>

<script>
import HeartIcon from "../../Icons/HeartIcon";
import BookmarkIcon from "../../Icons/BookmarkIcon";
import MessageIcon from "../../Icons/MessageIcon";
export default {
  name: "MainCard",
  components: {
    MessageIcon,
    BookmarkIcon,
    HeartIcon
  },
  props: {
    posts: {
      type: Array,
      default: () => ([]),
    }
  },
  data: () => ({
    model: 0,
    colors: [
      'primary',
      'secondary',
      'yellow darken-2',
      'red',
      'orange',
    ],
  }),
}
</script>


<style scoped lang="scss">
$style: "card";
.#{$style} {
  /* Common card style */
  max-width: 368px;
  max-height: 501px;
  border: 1px solid $color-gray-gallery;
  border-radius: 10px;
  &__cards-wrapper {
    display: flex;
  }
  &__text-content {
    padding: 40px 40px 25px 40px;
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
    @include text(12px, 400, $color-gray-alum);
    font-family: $helvetica;
    letter-spacing: -0.15px;
    line-height: 16px;
    margin-bottom: 17px;
  }
  &__description {
    @include text(14px, 400, $color-grey-oslo);
    font-family: $helvetica;
    letter-spacing: -0.16px;
    line-height: 18px;
    text-align: left;
  }
  &__footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 17px 40px 15px 40px;
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
  }
  &__icon-counter {
    @include text(14px, 300, $color-gray-alum);
    font-family: $helvetica-light;
    letter-spacing: -0.16px;
    margin-left: 8px;
  }

  /* Large card style */
  &--large {
    display: flex;
    flex-direction: row;
    max-width: 768px;
  }
  &__large-content {}
}
</style>