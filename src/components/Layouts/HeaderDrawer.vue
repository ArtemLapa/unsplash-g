<template>
  <div>
    <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>
    <v-navigation-drawer
      v-model="drawer"
      absolute
      temporary
      height="100vh"
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item
            v-for="item in items" :key="item.id"
            router :to="item.route"
          >
            <v-list-item-icon>
              <v-icon>mdi-home</v-icon>
            </v-list-item-icon>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>

        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  name: "HeaderDrawer",
  data: () => ({
    drawer: false,
    group: null,
    items: [
      {id: 0, title: "Home", route: "/"},
      {id: 1, title: "Featured collections", route: "/featured-collections"},
      {id: 2, title: "My profile", route: "/profile"},
    ]
  }),
}
</script>

<style scoped>
.v-overlay__scrim {
  height: 100vh;
}
</style>
