<template>
  <div class="dark:bg-slate-900 dark:text-slate-200 min-h-screen flex flex-col items-center justify-center gap-4">
    <h1>{{ $t('welcome') }}</h1>
    <div class="flex gap-2">
      <button class="border border-slate-500 p-2 rounded-xl" v-for="locale in locales" @click="setLocale(locale.code)">
        {{ locale.name }}
      </button>
    </div>
    <div class="mt-4">
      <p>{{ counterStore.count }}</p>
      <button class="border border-slate-500 p-2 rounded-xl" @click="counterStore.increment">
        increment
      </button>
    </div>
    <div>
      <h1>Color mode is: {{ colorMode.value }}</h1>
      <select v-model="colorMode.preference">
        <option value="light">Light</option>
        <option value="dark">Dark</option>
        <option value="system">System</option>
      </select>
    </div>
  </div>
</template>
<script setup lang="ts">
const { locales, setLocale } = useI18n()
const counterStore = useCounterStore()
const colorMode = useColorMode()
</script>