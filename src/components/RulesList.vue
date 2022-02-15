<template >
  <q-item-selection
    v-for="rule in rulesList"
    :key="rule.id"
    @click="alert('rule.action')"
  >
    Привет {{rule.id}}
  </q-item-selection>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'RulesList',
  props: {
    rulesList:{
      type: [],
      require: true,
    },
  },
});
</script>
