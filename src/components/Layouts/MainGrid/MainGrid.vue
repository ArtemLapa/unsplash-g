<template>
  <section class="main">
    <div class="my-container">
      <MainCard :posts="posts" />
    </div>
  </section>
</template>

<script>
import MainCard from "./MainCard";
export default {
  name: "MainGrid",
  components: {
    MainCard,
  },
  data: () => ({
    posts: [
      {
        id: 0,
        screen: require("@/assets/images/cards-images/screen-0.jpg"),
        author: "Tom Öhlin",
        location: "Indjinup Spa, WA, Australia (TAGS)",
        description:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam",
        bigCard: false,
      },
      {
        id: 1,
        screen: require("@/assets/images/cards-images/screen-1.jpg"),
        author: "Featured meal",
        location: "Served with french fries + drink",
        description:
          "Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper patty, Add Tender crisp patty and more.",
        bigCard: false,
      },
      {
        id: 2,
        screen: require("@/assets/images/cards-images/screen-2.jpg"),
        author: "Featured meal",
        location: "Served with french fries + drink",
        description:
          "Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper patty, Add Tender crisp patty and more. Add Tender crisp patty and more.",
        thumbnails: [
          "@/assets/images/card-3/carousel-item-0.jpg",
          "@/assets/images/card-3/carousel-item-1.jpg",
          "@/assets/images/card-3/carousel-item-2.jpg",
        ],
        bigCard: true,
      },
      {
        id: 3,
        screen: require("@/assets/images/cards-images/screen-2.jpg"),
        author: "Featured meal",
        location: "Served with french fries + drink",
        description:
          "Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper patty, Add Tender crisp patty and more. Add Tender crisp patty and more.",
        thumbnails: [
          "@/assets/images/card-3/carousel-item-0.jpg",
          "@/assets/images/card-3/carousel-item-1.jpg",
          "@/assets/images/card-3/carousel-item-2.jpg",
        ],
        bigCard: true,
      },
      {
        id: 4,
        screen: require("@/assets/images/cards-images/screen-1.jpg"),
        author: "Featured meal",
        location: "Served with french fries + drink",
        description:
          "Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper patty, Add Tender crisp patty and more.",
        bigCard: false,
      },
      {
        id: 5,
        screen: require("@/assets/images/cards-images/screen-0.jpg"),
        author: "Tom Öhlin",
        location: "Indjinup Spa, WA, Australia (TAGS)",
        description:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam",
        bigCard: false,
      },
      {
        id: 6,
        screen: require("@/assets/images/cards-images/screen-1.jpg"),
        author: "Featured meal",
        location: "Served with french fries + drink",
        description:
          "Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper patty, Add Tender crisp patty and more.",
        bigCard: false,
      },
      {
        id: 7,
        screen: require("@/assets/images/cards-images/screen-0.jpg"),
        author: "Tom Öhlin",
        location: "Indjinup Spa, WA, Australia (TAGS)",
        description:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam",
        bigCard: false,
      },
      {
        id: 8,
        screen: require("@/assets/images/cards-images/screen-1.jpg"),
        author: "Featured meal",
        location: "Served with french fries + drink",
        description:
          "Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper patty, Add Tender crisp patty and more.",
        bigCard: false,
      },
      {
        id: 9,
        screen: require("@/assets/images/cards-images/screen-0.jpg"),
        author: "Tom Öhlin",
        location: "Indjinup Spa, WA, Australia (TAGS)",
        description:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam",
        bigCard: false,
      },
    ],
  }),
};
</script>

<style scoped lang="scss">
$style: "main";
.#{$style} {
  display: flex;
  margin-bottom: 100px;
}
</style>
