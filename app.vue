<template>
  <div :dir="head.htmlAttrs.dir">
    <NuxtPage />
  </div>
</template>

<script setup>
const head = useLocaleHead({
  addDirAttribute: true,
  identifierAttribute: 'id',
  addSeoAttributes: true
})
</script>
