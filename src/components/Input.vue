<template>
  <input
    class="input"
    type="text"
  />
</template>

<script lang="ts" setup>
import { defineComponent } from 'vue';

interface InputFactoryProps {
  isEmpty: boolean;
  isDurty: boolean;
}

</script>

<style lang="scss">

.input {
  display: grid;
  grid-template-columns: 1fr 1fr;
  width: fit-content;
  column-gap: 10px;
  padding: 30px 0px;
}
</style>