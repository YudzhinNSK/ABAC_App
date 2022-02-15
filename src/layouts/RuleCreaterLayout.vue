<template>
  <q-layout
    style="
      flex-direction: row;
      display: flex;
      justify-content: space-around;
      height: fit-content;
      min-height: 0px;
    "
  >
    <q-select
      outlined
      v-model="attribute"
      :options="attributeSelectMocData"
      label="Аттрибут"
      style="width: 30%"
    />

    <q-select
      outlined
      v-model="action"
      :options="actionSelectMocData"
      label="Действие"
      style="width: 30%"
    />

    <q-input outlined v-model="value" label="Значение" style="width: 30%" />
  </q-layout>
  <template v-if="attribute && action && value">
    <q-btn
      class="q-mt-xl"
      color="white"
      text-color="blue"
      unelevated
      label="Добавить правило"
      no-caps
      @click="createRule"
    />
  </template>
  <template v-if="rulesList.length">
    <RulesList v-bind:rules-list="rulesList" />
  </template>
</template>

<script lang="ts">
import { ref } from 'vue';
import RulesList from '../components/RulesList.vue';

export default {
  setup() {
    const attributeSelectMocData = ['Имя', 'E-Mail', 'Роль'];

    const actionSelectMocData = ['<', '>', '>=', '<=', '=', '!=', 'in'];

    let action = ref(null);
    let attribute = ref(null);
    let value = ref(null);

    const rulesList: {
      action: string;
      attribute: string;
      value: string;
      id: number;
    }[] = [];

    return {
      attributeSelectMocData,
      actionSelectMocData,
      createRule() {
        const rule = {
          action: String(action.value),
          attribute: String(attribute.value),
          value: String(value.value),
          id: rulesList.length + 1,
        };
        rulesList.push(rule);
        action.value = null;
        attribute.value = null;
        value.value = null;
        console.log(rulesList);
      },
      action,
      attribute,
      value,
      rulesList,
    };
  },
  components: {
    RulesList,
  },
};
</script>
