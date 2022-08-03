<template>
  <div>
    <button
      class="btn-add"
    > Inserir
    </button>
  </div>
</template>

<script lang="ts" setup>
import InputField from './InputField.vue'
import TaskArea from './TaskArea.vue'

const taskList = []

if (InputField.value !== '') {
  taskList.push(InputField.value)
} else {
  window.alert('Por Favor, insira uma tarefa.')
}
</script>

<style lang="scss">

.btn-add {
  width: 60px;
  color: $text;
  background-color: $bg-input;
  border: $borders  1px solid;
  border-radius: 3px;
  box-shadow: none;
  padding: 5px 10px;
}

</style>
