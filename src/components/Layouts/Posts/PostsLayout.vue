<template>
  <section class="posts">
    <v-container>
<!--      <PostCard :posts="posts"/>-->
      <PostCardNew :posts="posts"/>
    </v-container>
  </section>
</template>

<script>
// import PostCard from "./PostCard";
import PostCardNew from "@/components/Layouts/Posts/PostCardNew";

export default {
  name: "MainGrid",
  components: {
    // PostCard,
    PostCardNew
  },
  data: () => ({
    posts: [
      {
        id: 0,
        screen:
          "https://images.unsplash.com/photo-1634897709221-55dff5c3a6bd?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1074&q=80",
        author: "Tom Öhlin",
        location: "Indjinup Spa, WA, Australia (TAGS)",
        description:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam",
        largeCard: false,
      },
      {
        id: 1,
        screen: require("@/assets/images/cards-images/screen-1.jpg"),
        author: "Featured meal",
        location: "Served with french fries + drink",
        description:
          "Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper patty, Add Tender crisp patty and more.",
        largeCard: false,
      },
      {
        id: 2,
        screen: require("@/assets/images/cards-images/screen-2.jpg"),
        author: "Featured meal",
        location: "Served with french fries + drink",
        description:
          "Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper patty, Add Tender crisp patty and more. Add Tender crisp patty and more.",
        thumbnails: [
          "https://images.unsplash.com/photo-1634897709221-55dff5c3a6bd?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1074&q=80",
          "https://images.unsplash.com/photo-1634794223755-e643735e62c6?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1074&q=80",
          "https://images.unsplash.com/photo-1627593872211-47ad3b412bee?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1470&q=80",
          "https://images.unsplash.com/photo-1633047612321-cbd69270a08b?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1476&q=80"
        ],
        largeCard: true,
      },
      {
        id: 3,
        screen: require("@/assets/images/cards-images/screen-2.jpg"),
        author: "Featured meal",
        location: "Served with french fries + drink",
        description:
          "Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper patty, Add Tender crisp patty and more. Add Tender crisp patty and more.",
        thumbnails: [
          "https://images.unsplash.com/photo-1634897709221-55dff5c3a6bd?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1074&q=80",
          "https://images.unsplash.com/photo-1634794223755-e643735e62c6?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1074&q=80",
          "https://images.unsplash.com/photo-1627593872211-47ad3b412bee?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1470&q=80",
          "https://images.unsplash.com/photo-1633047612321-cbd69270a08b?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1476&q=80"
        ],
        largeCard: true,
      },
      {
        id: 4,
        screen: require("@/assets/images/cards-images/screen-1.jpg"),
        author: "Featured meal",
        location: "Served with french fries + drink",
        description:
          "Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper patty, Add Tender crisp patty and more.",
        largeCard: false,
      },
      {
        id: 5,
        screen: require("@/assets/images/cards-images/screen-0.jpg"),
        author: "Tom Öhlin",
        location: "Indjinup Spa, WA, Australia (TAGS)",
        description:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam",
        largeCard: false,
      },
      {
        id: 6,
        screen: require("@/assets/images/cards-images/screen-1.jpg"),
        author: "Featured meal",
        location: "Served with french fries + drink",
        description:
          "Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper patty, Add Tender crisp patty and more.",
        largeCard: false,
      },
      {
        id: 7,
        screen: require("@/assets/images/cards-images/screen-0.jpg"),
        author: "Tom Öhlin",
        location: "Indjinup Spa, WA, Australia (TAGS)",
        description:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam",
        largeCard: false,
      },
      {
        id: 8,
        screen: require("@/assets/images/cards-images/screen-1.jpg"),
        author: "Featured meal",
        location: "Served with french fries + drink",
        description:
          "Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper patty, Add Tender crisp patty and more.",
        largeCard: false,
      },
      {
        id: 9,
        screen: require("@/assets/images/cards-images/screen-0.jpg"),
        author: "Tom Öhlin",
        location: "Indjinup Spa, WA, Australia (TAGS)",
        description:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam",
        largeCard: false,
      },
    ],
  }),
};
</script>

<style scoped lang="scss">
$style: "posts";
.#{$style} {
  //display: flex;
  margin-bottom: 100px;
}
</style>
