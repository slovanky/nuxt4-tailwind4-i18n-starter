<template>
  <Html :lang="locale" :dir="isRtl ? 'rtl' : 'ltr'">
    <Body>
      <NuxtLayout>
        <NuxtPage />
      </NuxtLayout>
    </Body>
  </Html>
</template>

<script setup lang="ts">
import { useI18n } from "vue-i18n";

const { locale } = useI18n();

const isRtl = computed(() => ["ar", "he", "fa"].includes(locale.value));
</script>
