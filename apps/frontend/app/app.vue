<template>
  <div>
    <h1>{{ $t('welcome') }}</h1>
    <div class="flex gap-2">
      <button class="border border-slate-500 p-2 rounded-xl" v-for="locale in locales" @click="setLocale(locale.code)">
        {{ locale.name }}
      </button>
    </div>
  </div>
</template>
<script setup lang="ts">
const { locales, setLocale } = useI18n()
</script>