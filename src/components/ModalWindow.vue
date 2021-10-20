<template>
  <div class="text-center">
    <v-dialog v-model="dialog" class="modal__dialog">
      <template v-slot:activator="{ on, attrs }">
        <v-btn color="red lighten-2" dark v-bind="attrs" v-on="on">
          Click Me
        </v-btn>
      </template>

      <v-card>
        <div class="modal">
          <div class="modal__container">
            <v-btn color="primary" text @click="dialog = false">
              <CrossIcon />
            </v-btn>
          </div>
        </div>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
import CrossIcon from "../components/Icons/CrossIcon.vue";
export default {
  name: "ModalWindow",
  components: {
    CrossIcon,
  },
  data: () => ({
    dialog: false,
  }),
};
</script>
<style lang="scss">
.v-dialog {
  max-width: 1104px;
  height: 1169px;
}
</style>
<style lang="scss" scoped>
$style: "modal";
.#{$style} {
  height: 1169px;
  background-color: $color-white;
  &__container {
    max-width: 1032px;
    width: 100%;
    margin: auto;
  }
}
</style>
