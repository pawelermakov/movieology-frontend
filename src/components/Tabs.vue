<script lang="ts" setup>
import { Tab } from '../types'

defineProps<{
  tabs: Tab[]
  activeTab: string
}>()

const emits = defineEmits<{
  (e: 'on-tab-change', tab: string): void
}>()
</script>

<template>
  <div>
    <nav class="flex space-x-4 mx-4">
      <a
        class="rounded-lg px-5 py-2 text-white drop-shadow-sm hover:bg-oranje cursor-pointer"
        :class="id == activeTab ? 'bg-oranje' : 'bg-movie-black-200'"
        v-for="{ id, emoji, title } in tabs"
        :key="id"
        @click="emits('on-tab-change', id)"
      >
        {{ emoji }}
        {{ title }}
      </a>
    </nav>
  </div>
</template>
