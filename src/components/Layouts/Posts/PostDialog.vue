<template>
  <div class="post-dialog text-center">
    <v-dialog
      v-model="dialog"
      max-width="1104"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-img
          v-bind="attrs"
          v-on="on"
          max-height="258"
          src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
          class="post-dialog__card-image"
        />
      </template>

      <v-card
        max-width="1104"
        class="post-dialog__card"
      >
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="black"
            text
            @click="dialog = false"
          >
            <v-icon>mdi-window-close</v-icon>
          </v-btn>
        </v-card-actions>

        <div class="post-dialog__first-img">
          <v-img src="https://cdn.vuetifyjs.com/images/cards/cooking.png" max-height="644" max-width="1032"/>
        </div>

        <div class="post-dialog__author">
          <v-avatar
            color="primary"
            size="86"
            class="post-dialog__avatar"
          >
            <v-img src="https://shorturl.at/dnER9" alt="Name"/>
          </v-avatar>

          <div class="post-dialog__author-info">
            <h3 class="post-dialog__name">Stephanie Hau</h3>
            <span class="post-dialog__nickname">@stephiime</span>
          </div>
        </div>

        <div class="post-dialog__images-grid">
          <v-img
            v-for="n in 12"
            :key="n"
            :src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
            :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`"
            aspect-ratio="1"
            class="post-dialog__grid-image grey lighten-2"
          ></v-img>
        </div>

      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  name: "PostDialog",
  data: () => ({
    dialog: false,
  })
}
</script>

<style lang="scss" scoped>
$style: "post-dialog";
.#{$style} {
  &__card-image {
    border-radius: 8px 8px 0 0;
    height: 230px;
    cursor: pointer;
    @include media($screen-desktop) {
      height: 258px;
    }

    &--large {
      border-radius: 8px 0 0 8px;
      max-height: 501px;
      height: 100%;
      max-width: 368px;
      width: 100%;
    }
  }

  &__card {
    padding: 0 10px 20px 10px;
    @include media($screen-desktop) {
      max-height: 1169px;
      padding: 20px 36px 50px;
    }
  }

  &__first-img {
    margin-bottom: 37px;
  }

  &__author {
    display: flex;
    align-items: center;
    margin-bottom: 33px;
  }

  &__avatar {
    margin-right: 26px;
  }

  &__author-info {
    font-stretch: normal;
    font-style: normal;
  }

  &__name {
    @include text(18px, 500, $color-green-rangoon);
    font-family: $helvetica-medium;
    line-height: normal;
    letter-spacing: -0.23px;
    margin-bottom: 3px;
  }

  &__nickname {
    @include text(12px, normal, $color-gray-alum);
    line-height: 1.33;
    letter-spacing: -0.15px;
  }

  &__images-grid {
    display: grid;
    grid-template-columns: minmax(auto, 300px) minmax(auto, 300px);
    row-gap: 10px;
    column-gap: 10px;

    @include media($screen-tablet-small) {
      grid-template-columns: minmax(auto, 300px) minmax(auto, 300px) minmax(auto, 300px);
    }

    @include media($screen-netbook) {
      grid-template-columns: minmax(auto, 330px) minmax(auto, 300px) minmax(auto, 300px);
    }

    @include media($screen-desktop) {
      grid-template-columns: minmax(auto, 199px) minmax(auto, 133px) minmax(auto, 133px) minmax(auto, 199px) minmax(auto, 133px) minmax(auto, 133px);
      row-gap: 15px;
      column-gap: 15px;
    }
  }

  &__grid-image {
    max-height: 161px;
    @include media($screen-desktop) {
      max-height: 131px;
    }
  }
}
</style>
