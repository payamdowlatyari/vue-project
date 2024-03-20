<template>
    <button @click="toggleDark()">
      <i inline-block align-middle i="dark:carbon-moon carbon-sun" />
  
      <span class="ml-2">{{ isDark ? 'Dark' : 'Light' }}</span>
    </button>
  </template>

<script>
/* eslint-disable */

import { useDark, useToggle } from '@vueuse/core'

const isDark = useDark()
const toggleDark = useToggle(isDark)

export default {
    name: 'ThemeSwitch',
    props: {
        isDark: String,
        toggleDark
    }
}
</script>

