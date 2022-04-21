<script setup>
import { ref } from 'vue'
const header = ref(true)
const showMenu = ref(true)

function handlerHeader () {
  header.value = !(header.value)
}
function onReveal (value) {
  console.log(value)
}

function handlerMenu () {
  showMenu.value = !showMenu.value
}
</script>

<template>
  <q-layout view="HHH lpr FFF">
    <q-header class="header bg-white" @reveal="onReveal" reveal elevated v-model="header">
      <q-toolbar class="text-primary" >
        <q-btn @click="handlerMenu" flat round dense icon="menu" />
        <q-space></q-space>
        <q-toolbar-title class="text-center">Quasar Framework</q-toolbar-title>
        <q-btn flat round dense icon="more_vert" />
      </q-toolbar>
      <q-toolbar v-show="showMenu" class="bg-primary" inset>
        <q-toolbar-title>Let yours dream come true</q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-footer v-model="header">
      <q-toolbar class="text-center ">
        <q-toolbar-title class="toolbar text-strike">Bye</q-toolbar-title>
      </q-toolbar>
    </q-footer>

    <q-page-container class="flex center">
      <q-page class="q-pa-md">
        <q-btn @click="handlerHeader" label="click me"></q-btn>

      </q-page>
    </q-page-container>

  </q-layout>
</template>

<style scoped>
.header{
  background-color: blueviolet;
}
.toolbar{
  font-size: 18px;
  font-weight: 300;
}
</style>
