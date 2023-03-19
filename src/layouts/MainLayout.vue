<template>
  <q-layout view="hHh lpR fFf">
    <q-header class="bg-teal-6 text-white" reveal>
      <q-toolbar>
        <q-toolbar-title>
          <q-icon name="medical_services" size="xl" class=""></q-icon>
          <q-btn
            flat
            size="lg"
            to="#"
            class="indexbtn"
            style="padding-top: 10px"
            >泰山耳鼻喉科
          </q-btn>
        </q-toolbar-title>

        <q-drawer
          class="lt-md text-center bg-teal"
          v-model="rightDrawerOpen"
          side="right"
          bordered
        >
          <q-tabs class="lt-md text-white" vertical v-model="tab">
            <q-tab name="home" label="HOME" href="#" />
            <q-tab name="skill" label="SKILL" href="#skill" />
            <q-tab name="about" label="ABOUT" href="#about" />
            <q-tab name="portfolio" label="PORTFOLIO" href="#portfolio" />
            <q-tab name="contact" label="CONTACT" href="#contact" />
          </q-tabs>
        </q-drawer>
        <q-tabs class="gt-sm" v-model="tab">
          <q-tab name="home" label="HOME" href="#" />
          <q-tab name="skill" label="SKILL" href="#skill" />
          <q-tab name="about" label="ABOUT" href="#about" />
          <q-tab name="portfolio" label="PORTFOLIO" href="#portfolio" />
          <q-tab name="contact" label="CONTACT" href="#contact" />
        </q-tabs>

        <q-btn
          flat
          icon="menu"
          @click="toggleRightDrawer"
          class="lt-md q-pt-xs"
          size="md"
        />
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'

const tab = ref('top')
const rightDrawerOpen = ref(false)

function toggleRightDrawer () {
  rightDrawerOpen.value = !rightDrawerOpen.value
}

</script>
