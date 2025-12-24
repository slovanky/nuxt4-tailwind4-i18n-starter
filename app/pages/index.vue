<template>
  <div class="min-h-screen flex flex-col items-center justify-center bg-gray-50 text-gray-900 p-4">
    <div class="max-w-md w-full text-center space-y-6">
      <h1 class="text-4xl font-bold tracking-tight">
        {{ $t('welcome') }}
      </h1>
      <p class="text-lg text-gray-600">
        {{ $t('description') }}
      </p>
      
      <div class="flex justify-center gap-4 pt-4">
        <NuxtLink
          v-for="locale in availableLocales"
          :key="locale.code"
          :to="switchLocalePath(locale.code)"
          class="px-4 py-2 rounded-lg bg-white border border-gray-200 shadow-sm hover:bg-gray-50 transition-colors font-medium"
        >
          {{ locale.name }}
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup>
const { locale, locales, t } = useI18n()
const switchLocalePath = useSwitchLocalePath()

const availableLocales = computed(() => {
  return locales.value.filter(i => i.code !== locale.value)
})

useHead({
  title: t('welcome')
})
</script>
