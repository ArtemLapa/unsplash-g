<template>
  <section class="main">
    <div class="container">
      <MainCard :posts="posts"/>
    </div>
  </section>
</template>

<script>
import MainCard from "./MainCard";
export default {
  name: "MainGrid",
  components: {
    MainCard
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
        bigCard: false
      },
      {
        id: 2,
        screen: require("@/assets/images/cards-images/screen-2.jpg"),
        author: "Featured meal",
        location: "Served with french fries + drink",
        description:
            "Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper patty, Add Tender crisp patty and more. Add Tender crisp patty and more.",
        "carousel-items": [
          "@/assets/images/carousel-item-0",
          "@/assets/images/carousel-item-1",
          "@/assets/images/carousel-item-2",
        ],
        bigCard: true
      }
    ]
  })
}
</script>

<style scoped lang="scss">
$style: "main";
.#{$style} {
  display: flex;
  margin-bottom: 100px;
}
</style>