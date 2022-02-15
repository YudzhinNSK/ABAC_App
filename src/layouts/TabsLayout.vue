<template>
  <q-btn
    class="q-mt-xl"
    color="white"
    text-color="blue"
    unelevated
    to="/"
    label="На главную страницу"
    no-caps
  />
  <div class="q-pa-md" style="display: flex; justify-content: center">
    <div class="q-gutter-y-md" style="width: 1000px">
      <q-card>
        <q-tabs
          v-model="tab"
          dense
          class="text-grey"
          active-color="primary"
          indicator-color="primary"
          align="justify"
          narrow-indicator
        >
          <q-tab name="rules" label="Создание правила" />
          <q-tab name="policy" label="Создание политики" />
          <q-tab name="policySet" label="Создание набора политик" />
          <q-tab name="resources" label="Окружение" />
        </q-tabs>

        <q-separator />

        <q-tab-panels v-model="tab" animated>
          <q-tab-panel name="rules">
            <RuleCreaterLayout />
          </q-tab-panel>

          <q-tab-panel name="policy">
            <PoliticCreateLayout />
          </q-tab-panel>

          <q-tab-panel name="policySet">
            <PoliticsSetCreateLayout />
          </q-tab-panel>

          <q-tab-panel name="resources">
            <ResourcesLayout />
          </q-tab-panel>
        </q-tab-panels>
      </q-card>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';
import RuleCreaterLayout from './RuleCreaterLayout.vue';
import PoliticCreateLayout from './PoliticCreateLayout.vue';
import PoliticsSetCreateLayout from './PoliticsSetCreateLayout.vue';
import ResourcesLayout from './ResourcesLayout.vue';

export default {
  setup() {
    return {
      tab: ref('rules'),
    };
  },
  components: {
    RuleCreaterLayout,
    PoliticCreateLayout,
    PoliticsSetCreateLayout,
    ResourcesLayout,
  },
};
</script>
