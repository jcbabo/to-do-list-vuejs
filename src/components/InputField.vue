<template>
  <input class="input-area" type="text" />
</template>

<script lang="ts" setup>

interface InputFactoryProps {
  isEmpty: boolean;
  isDurty: boolean;
}

const taskList = []

// addTask(){

// }
</script>

<style lang="scss">
.input-area {
  color: $text;
  background-color: $bg-input;
  border: $borders 1px solid;
  border-radius: 3px;
  box-shadow: none;
  padding: 5px 10px;
}
</style>
