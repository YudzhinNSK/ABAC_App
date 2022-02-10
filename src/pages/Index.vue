<template>
  <q-page class="row items-center justify-evenly">
    <button @click="buttonClick">
      Текст кнопки
    </button>
  </q-page>
</template>

<script lang="ts">
import { defineComponent} from 'vue';

export default defineComponent({
  name: 'PageIndex',
  methods:{
    buttonClick(){
      console.log('click');
      alert('click');
    }
  },

});
</script>
