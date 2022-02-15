<template>
  <q-page class="column items-center justify-center">
    Здравствуйте! Вы находитесь на главной странице ABAC на объекте Демо 1
    <button @click="this.$router.push('/create_rule');" style="margin-top: 40px;">
      Создать политику
    </button>
  </q-page>
</template>

<script lang="ts">
import { defineComponent} from 'vue';

export default defineComponent({
  name: 'PageIndex',
});
</script>
