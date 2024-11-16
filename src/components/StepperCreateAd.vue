<template>
  <q-stepper
    v-model="currentStep"
    flat
    bordered
  >
    <q-step
      v-for="step in steps"
      :key="step.name"
      :name="step.name"
      :title="step.title"
      :done="currentStep > step.name"
    >
      <div class="q-pa-md">
        {{ step.content }}
      </div>
      <q-btn
        v-if="currentStep < steps.length"
        color="primary"
        label="Próximo"
        @click="nextStep"
      />
    </q-step>
  </q-stepper>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'MyStepper',
  setup() {
    const currentStep = ref<number>(1);

    const steps = ref([
      { name: 1, title: 'Primeiro Passo', content: 'Conteúdo do primeiro passo' },
      { name: 2, title: 'Segundo Passo', content: 'Conteúdo do segundo passo' },
      { name: 3, title: 'Terceiro Passo', content: 'Conteúdo do terceiro passo' },
    ]);

    const nextStep = () => {
      if (currentStep.value < steps.value.length) {
        currentStep.value++;
      }
    };

    return {
      currentStep,
      steps,
      nextStep,
    };
  },
});
</script>
