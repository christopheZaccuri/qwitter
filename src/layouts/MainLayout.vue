<template>
  <q-layout view="lHr lpR fFf">

    <q-header elevated class="bg-white text-grey-9">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />

        <q-toolbar-title>
          Qwitter
        </q-toolbar-title>

        <q-btn dense flat round icon="menu" @click="toggleRightDrawer" />
      </q-toolbar>
    </q-header>

    <q-drawer
      show-if-above
      v-model="leftDrawerOpen"
      side="left"
      bordered
      class="q-pa-lg"
    >
      <q-icon
        name="fa-solid fa-kiwi-bird"
        size="md"
        color="primary"
      />
      <div class="q-pa-md" style="max-width: 350px">
        <q-list>
          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-icon color="dark" name="fa-solid fa-house-user" />
            </q-item-section>
            <q-item-section>Accueil</q-item-section>
          </q-item>
          <q-item clickable v-ripple to="/Explorer">
            <q-item-section avatar>
              <q-icon color="dark" name="fa-light fa-hashtag" />
            </q-item-section>
            <q-item-section>Explorer</q-item-section>
          </q-item>
          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-icon color="dark" name="fa-solid fa-bell" />
            </q-item-section>
            <q-item-section>Notifications</q-item-section>
          </q-item>
          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-icon color="dark" name="fa-solid fa-envelope" />
            </q-item-section>
            <q-item-section>Messages</q-item-section>
          </q-item>
        </q-list>
      </div>
    </q-drawer>

    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>
      <!-- drawer content -->
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const leftDrawerOpen = ref(false)
    const rightDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      },

      rightDrawerOpen,
      toggleRightDrawer () {
        rightDrawerOpen.value = !rightDrawerOpen.value
      }
    }
  }
}
</script>