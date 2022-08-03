<template>
  <div>
    <input
    type="checkbox"
    id="task-checkbox"
    class="class-task-checkbox">
    <input
    type="text"
    id="task-text"
    class="class-task-text">
  </div>
</template>
<script lang="ts" setup>

</script>
<style lang="scss">
.class-task-checkbox {
  display: inline-flex;
  text-decoration: none;
  border: 1px solid $borders;
  background-color: $bg-input;
}

.class-task-text {
  text-decoration: underline;
  border: none;
  background-color: $bg-page;
  color: $text;
}
</style>
