<template>
  <q-page class="row items-center justify-evenly">
    <!-- <div class="q-pa-md row items-start q-gutter-md"> -->
    <div class="my-card q-ma-md row items-start q-gutter-xs">
      <q-card class="child-card col-2" flat bordered v-for="n in 5" :key="n">
        <q-img src="https://cdn.quasar.dev/img/chicken-salad.jpg" />

        <q-card-section>
          <q-btn
            fab
            color="primary"
            icon="place"
            class="absolute"
            style="top: 0; right: 12px; transform: translateY(-50%)"
          />

          <div class="row no-wrap items-center">
            <div class="col text-h6 ellipsis">Cafe Basilico</div>
            <div
              class="col-auto text-grey text-caption q-pt-md row no-wrap items-center"
            >
              <q-icon name="place" />
              250 ft
            </div>
          </div>
        </q-card-section>

        <q-card-section class="q-pt-none">
          <div class="text-subtitle1">$・Italian, Cafe</div>
          <div class="text-caption text-grey">
            Small plates, salads & sandwiches in an intimate setting.
          </div>
        </q-card-section>

        <q-separator />

        <q-card-actions>
          <q-btn flat round icon="event" />
          <q-btn flat color="primary"> Reserve </q-btn>
        </q-card-actions>
      </q-card>
    </div>
  </q-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'IndexPage',

  components: {},

  data() {
    return {};
  },
});
</script>

<style scoped>
.my-card {
  width: 90%;
  height: 100%;
  border-radius: 12px;
  background-color: white;
}
.child-card {
  width: 200px;
  height: 200px;
}
</style>
