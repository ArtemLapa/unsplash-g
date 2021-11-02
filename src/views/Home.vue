<template>
  <div>
    <Preview/>
    <MainGrid/>
  </div>
</template>

<script>
import Preview from "../components/Preview";
import MainGrid from "../components/Layouts/Posts/PostsLayout";

export default {
  name: "Home",
  components: {
    MainGrid,
    Preview,
  },
};
</script>
