<template>
  <q-layout view="lHh lpR fFf">
    <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered class="text-white" :width="340">
      <!-- drawer content -->
      <q-scroll-area class="fit q-pa-lg q-pt-lg">
        <!-- div class="q-pa-lg q-pt-lg" -->
        <q-toolbar>
          <img src="~assets/Logo.svg">
        </q-toolbar>
        <q-toolbar class="q-mb-xl">
          <span class="caption text-subtitle2">
            Trusted way of banking for 3,000+ SMEs and startups in Singapore
          </span>
        </q-toolbar>
        <!--q-list-->
        <q-item v-for="link in links" :key="link.text" clickable class="q-mt-xl q-mb-xl">
          <q-item-section avatar>
            <q-icon color="grey" :name="link.icon" />
          </q-item-section>
          <q-item-section>
            <q-item-label>{{ link.text }}</q-item-label>
          </q-item-section>
        </q-item>
        <!--/q-list-->
        <!--/div -->
      </q-scroll-area>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer elevated class="bg-white lt-md">
      <q-toolbar>
        <q-toolbar-title>
          <q-tabs v-model="tab" class="bg-white text-grey-4">
            <q-tab v-for="link in links" :key="link.text" :icon="link.tabicon" :label="link.text" class="q-px-xs q-py-xs"></q-tab>
          </q-tabs>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  data() {
    return {
      tab: 'Home'
    }
  },
  setup() {
    const leftDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value
      },
      links: [
        { icon: "img:icons/Home.svg", text: 'Home', tabicon: "img:icons/Logo1.svg" },
        { icon: 'img:icons/Card.svg', text: 'Cards', tabicon: "img:icons/Card.svg" },
        { icon: 'img:icons/Payments.svg', text: 'Payments', tabicon: "img:icons/Payments1.svg" },
        { icon: 'img:icons/Credit.svg', text: 'Credit', tabicon: "img:icons/Credit1.svg" },
        { icon: 'img:icons/Account.svg', text: 'Settings', tabicon: "img:icons/Account1.svg" }
      ],
    }
  }
}
</script>
<style lang="sass">
.q-drawer
  background: #0C365A !important

.caption
  opacity: 30%
  font-size: 14px

.q-tab__label 
  font-size: 12px 
.q-tab__content img
  width: 15px
  height: 15px
</style>