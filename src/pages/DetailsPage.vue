<template>
  <q-page class="column items-center">
    <div class="column items-start" style="width: 1200px">
      <q-btn
        class="q-my-sm"
        label="Voltar aos anúncios"
        flat
        dense
        color="primary"
        no-caps
        to="/"
      />
    </div>
    <div class="row mv-container-card justify-start items-start content-start">
      <div class="col-5">
        <div class="q-ma-lg">
          <q-img
            style="height: 600px; border-radius: 12px"
            src="https://cdn.quasar.dev/img/chicken-salad.jpg"
          />
        </div>
        <div class="row q-mx-lg">
          <q-virtual-scroll
            :items="listImg"
            virtual-scroll-horizontal
            v-slot="{ item, index }"
          >
            <q-avatar class="q-mx-sm" :key="index" rounded size="80px">
              <img :src="item.url" />
            </q-avatar>
          </q-virtual-scroll>
        </div>
      </div>
      <div class="col-7 column justify-between" style="height: 100%">
        <div class="q-mr-md col-12" style="height: 640px;">
          <div class="column items-end q-mt-sm q-mr-sm">
            <q-btn outline round color="primary" icon="more_vert" />
          </div>
          <div
            class="text-h5 text-weight-bold text-grey q-mt-lg q-mr-lg q-mb-lg"
          >
            Titulo do anúncio
          </div>
          <div class="text-subtitle1 text-primary text-weight-regular q-pb-md">
            R$ 526.55
          </div>
          <div class="text-subtitle1 text-weight-bold text-secondary">
            Descrição do anúncio
          </div>
          <div class="text-subtitle2 text-grey-6 q-mt-xs">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
            aliquip ex ea commodo consequat.
          </div>
          <q-separator class="q-my-md" />
          <div class="text-subtitle1 text-weight-bold text-secondary q-mt-lg">
            Detalhes
          </div>
          <div class="text-subtitle2 text-grey-6 q-mt-xs">
            Lorem ipsum dolor sit amet
          </div>
          <div class="text-subtitle2 text-grey-6 q-mt-xs">
            Lorem ipsum dolor sit amet
          </div>
          <div class="text-subtitle2 text-grey-6 q-mt-xs">
            Lorem ipsum dolor sit amet
          </div>
        </div>
        <div class="q-mr-md q-mt-xl q-mb-lg col-12 column items-center">
          <q-btn class="full-width" label="Entrar em contato" color="primary" no-caps />
        </div>
      </div>
    </div>
  </q-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

interface IListImg {
  id: number;
  url: string;
}

export default defineComponent({
  name: 'IndexPage',

  components: {},

  data(): { listImg: IListImg[] } {
    return {
      listImg: [
        {
          id: 1,
          url: 'https://cdn.quasar.dev/img/chicken-salad.jpg',
        },
        {
          id: 2,
          url: 'https://cdn.quasar.dev/img/chicken-salad.jpg',
        },
        {
          id: 3,
          url: 'https://cdn.quasar.dev/img/chicken-salad.jpg',
        },
        {
          id: 4,
          url: 'https://cdn.quasar.dev/img/chicken-salad.jpg',
        },
        {
          id: 5,
          url: 'https://cdn.quasar.dev/img/chicken-salad.jpg',
        },
        {
          id: 1,
          url: 'https://cdn.quasar.dev/img/chicken-salad.jpg',
        },
        {
          id: 2,
          url: 'https://cdn.quasar.dev/img/chicken-salad.jpg',
        },
        {
          id: 3,
          url: 'https://cdn.quasar.dev/img/chicken-salad.jpg',
        },
        {
          id: 4,
          url: 'https://cdn.quasar.dev/img/chicken-salad.jpg',
        },
        {
          id: 5,
          url: 'https://cdn.quasar.dev/img/chicken-salad.jpg',
        },
      ],
    };
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
</style>
