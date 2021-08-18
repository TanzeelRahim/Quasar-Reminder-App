<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="p-3 mb-50 bg-warning text-dark">
      <q-toolbar>
        <q-toolbar-title> Reminders </q-toolbar-title>
        <q-toolbar-text>
          <router-link to="/about">About App</router-link>
        </q-toolbar-text>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>
