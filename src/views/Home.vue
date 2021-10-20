<template>
  <div>
    <Preview />
    <MainGrid />
  </div>
</template>

<script>
// @ is an alias to /src

import Preview from "../components/Preview";
import MainGrid from "../components/Layouts/MainGrid/MainGrid";
export default {
  name: "Home",
  components: {
    MainGrid,
    Preview,
  },
};
</script>
