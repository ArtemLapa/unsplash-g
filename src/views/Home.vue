<template>
  <main>
    <Preview/>
    <MainGrid/>
  </main>
</template>

<script>
// @ is an alias to /src

import Preview from "../components/Preview";
import MainGrid from "../components/Layouts/MainGrid/MainGrid";
export default {
  name: "Home",
  components: {
    MainGrid,
    Preview
  }
}
</script>
