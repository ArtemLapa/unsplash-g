<template>
  <v-app>
    <Header />
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
import Header from "@/components/Layouts/Header";
export default {
  components: { Header },
};
</script>

<style lang="scss">
@import "scss/style";
</style>
