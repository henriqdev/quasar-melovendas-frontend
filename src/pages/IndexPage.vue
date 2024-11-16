<template>
  <q-page class="column items-center">
    <div
      class="mv-container-card row justify-start items-start content-start q-ma-md q-pa-lg"
    >
      <div class="q-pl-sm text-h5 text-secondary text-weight-medium col-12">
        Ultimos adicionados
      </div>
      <div class="col-xs-12 col-md-4 col-lg-3" v-for="n in 11" :key="n">
        <q-card class="q-ma-sm border-custom child-card" flat bordered>
          <q-img src="https://cdn.quasar.dev/img/chicken-salad.jpg" />

          <q-card-section>
            <div class="row column items-start">
              <div class="col-12 text-subtitle1" style="max-height: 60px">
                Bateria bacana /br toca facil até mesmo sozinho
              </div>
              <div class="col-12 text-secondary text-body2 q-py-sm">
                R$ 2.562,00
              </div>
              <q-btn
                unelevated
                no-caps
                class="col-12 full-width"
                color="primary"
                to="detalhamento"
              >
                ver detalhes
              </q-btn>
            </div>
          </q-card-section>
        </q-card>
      </div>
      <q-btn class="col-12 full-width" flat color="primary">
        Carregar mais
      </q-btn>
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

<style lang="scss" scope>
.mv-container-card {
  width: 1200px;
  height: 100%;
  border-radius: 12px;
  background-color: white;
}
.child-card {
  overflow: auto;
}
.border-custom {
  border: 2px solid $primary;
  border-radius: 8px;
}
</style>
