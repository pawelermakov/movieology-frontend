<script lang="ts" setup>
import { ref } from 'vue'
import Page from '../components/layout/Page.vue'
import MainBanner from '../components/MainBanner.vue'
import FlashNews from '../components/FlashNews.vue'
import Tabs from '../components/Tabs.vue'

import { tabsMock } from '../mocks/tabs'
import ContentRow from '../components/ContentRow.vue'

const activeTab = ref<string>(tabsMock[0].id)
const onTabChange = (tabId: string) => {
  activeTab.value = tabId
}
</script>

<template>
  <page>
    <template #title>Home</template>
    <div>
      <tabs
        :tabs="tabsMock"
        :active-tab="activeTab"
        @on-tab-change="onTabChange"
      />
    </div>
    <content-row>
      <main-banner />
      <div class="ml-10 max-w-md w-full">
        <flash-news />
      </div>
    </content-row>
  </page>
</template>
