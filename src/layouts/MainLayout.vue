<template>
  <q-layout view="hHh LpR fff">
    <q-header reveal elevated class="bg-white text-primary">
      <q-toolbar>
        <q-space />
        <q-avatar class="q-mx-md" square style="width: 80px">
          <img src="icons/logo.png" />
        </q-avatar>
        <q-input
          class="q-px-xl"
          standout="bg-secondary text-white"
          v-model="searchMain"
          label="Pesquise por algo"
          dense
          color="primary"
          label-color="primary"
        >
          <template v-slot:append>
            <q-icon
              v-if="searchMain !== ''"
              name="close"
              @click="searchMain = ''"
              class="cursor-pointer"
            />
            <q-icon color="primary" name="search" />
          </template>
        </q-input>

        <q-btn class="q-mr-md" color="primary" label="Login" />
        <q-btn outline color="primary" label="Registrar" />
        <q-space />
      </q-toolbar>
    </q-header>

    <q-page-container class="bg-custom">
      <router-view />
    </q-page-container>

    <q-footer bordered class="bg-primary text-white">
      <q-toolbar>
        <q-toolbar-title> </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'MainLayout',

  components: {},

  data(): {
    searchMain: string;
  } {
    return {
      searchMain: '',
    };
  },

  methods: {},
});
</script>

<style scoped>
.bg-custom {
  background-color: #f2f2f2;
}
</style>
