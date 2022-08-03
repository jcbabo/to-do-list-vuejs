<template>
  <div class="app-container">
    <component :is="layout" class="dynamic-layout"></component>
  </div>
</template>

<script lang="ts">
import DefaultLayout from './layout/DefaultLayout.vue'
import { defineComponent, shallowRef } from 'vue'

export default defineComponent({
  name: 'App',
  setup () {
    const layout = shallowRef(DefaultLayout)
    const componentLayout = import(`./layout/${layout.value}.vue`)

    return {
      layout
    }
  }
})
</script>

<style lang="scss">
:root {
  font-size: 62.5%;
  font-family: 'Prompt', Sans-Serif;

  body {
    font-size: 1.7rem;
  }

  #app,
  .app-container {
    height: 100vh;
  }
}
</style>
