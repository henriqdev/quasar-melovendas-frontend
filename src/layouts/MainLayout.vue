<template>
  <q-layout view="hHh lpR fff">
    <q-header reveal elevated class="row justify-center bg-white text-primary">
      <q-toolbar class="row" style="max-width: 1220px">
        <div class="col-2">
          <q-avatar square style="width: 80px">
            <img src="images/logo.png" />
          </q-avatar>
        </div>
        <div class="col-6">
          <q-input
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
        </div>
        <div class="col-2 row justify-center">
          <q-btn
            outline
            color="primary"
            label="Criar anúncio"
            @click="dialogCreateAd = true"
          />
        </div>
        <div class="col-2 row justify-end">
          <q-btn color="primary" label="Login" class="q-mr-sm" />
          <q-btn outline color="primary" label="Registrar" />
        </div>
      </q-toolbar>
    </q-header>

    <q-page-container class="bg-custom">
      <router-view />
    </q-page-container>

    <q-footer bordered class="bg-primary text-white">
      <q-toolbar>
        <q-space />
        <div class="text-weight-thin text-center">
          MeloVendas feito com muito amor S2
        </div>
        <q-space />
      </q-toolbar>
    </q-footer>
    <q-dialog v-model="dialogCreateAd">
      <q-card style="width: 800px; max-width: 90vw">
        <q-card-section>
          <div class="q-ml-sm text-h5 text-primary text-weight-bold">
            Escolha o item que você pretende vender
          </div>
        </q-card-section>

        <q-card-section class="q-pt-none">
          <div class="row">
            <div class="col-6">
              <div
                class="border-custom height-card-dial row items-center q-ma-xs cursor-pointer"
                @click="goToCreateAd()"
              >
                <div class="row col-12 justify-center">
                  <q-avatar size="80px">
                    <img src="images/man-plays-guitar.png" />
                  </q-avatar>
                </div>
                <div class="col-12 text-h6 text-primary text-center">
                  Instrumentos
                </div>
                <div
                  class="text-center q-pa-sm text-grey-7 text-body1 text-weight-light"
                >
                  Crie um único anúncio para trocar seu instrumento por outro ou
                  até mesmo por algum item que você goste ou até mesmo vender.
                </div>
              </div>
            </div>
            <div class="col-6">
              <div
                class="border-custom height-card-dial row items-center q-ma-xs cursor-pointer"
              >
                <div class="row col-12 justify-center">
                  <q-avatar size="80px">
                    <img src="images/shopping-delivery.png" />
                  </q-avatar>
                </div>
                <div class="col-12 text-h6 text-primary text-center">
                  Outros itens
                </div>
                <div
                  class="text-center q-pa-sm text-grey-7 text-body1 text-weight-light"
                >
                  Anuncie um outro item relacionado a música para venda. Pode
                  ser algum curso, e-book, tablaturas ou partituras.
                </div>
              </div>
            </div>
            <div class="col-12" style="height: 100px">
              <div class="row border-custom row q-ma-xs cursor-pointer">
                <div class="col-1 row items-center justify-center">
                  <q-icon size="lg" color="primary" name="add" class="border-icon" />
                </div>
                <div class="col-11">
                  <div class="q-ml-md text-h6 text-primary">Itens Variados</div>
                  <div
                    class="text-center q-pa-sm text-grey-7 text-body1 text-weight-light"
                  >
                    Aqui você pode ser criativo. Vender aquele vídeo game que
                    você não usa mais ou aquela geladeira que ficou parada. Mas
                    lembre-se: esses anúncios ficarão apenas em seu perfil.
                  </div>
                </div>
              </div>
            </div>
          </div>
        </q-card-section>

        <q-card-actions align="right">
          <q-btn color="primary" flat label="Voltar" v-close-popup />
        </q-card-actions>
      </q-card>
    </q-dialog>
  </q-layout>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'MainLayout',

  components: {},

  data(): {
    searchMain: string;
    dialogCreateAd: boolean;
  } {
    return {
      searchMain: '',
      dialogCreateAd: false,
    };
  },

  methods: {
    goToCreateAd() {
      this.$router.push('/detalhamento')
    },
  },
});
</script>

<style lang="scss" scoped>
.bg-custom {
  background-color: #f2f2f2;
}
.border-custom {
  border: 1px solid $grey-4;
  border-radius: 8px;
}
.border-icon {
  border: 1px dashed $grey-6;
  border-radius: 25px;
  width: 50px;
  height: 50px;
}
.height-card-dial {
  height: 220px;
}
</style>
