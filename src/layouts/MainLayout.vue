<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          Menu
        </q-item-label>

        <q-item :to="{name: 'dashboard'}">
          <q-item-section avatar top>
            <q-avatar icon="home" color="blue" text-color="white" />
          </q-item-section>

          <q-item-section>
            <q-item-label lines="1">Home Page</q-item-label>
          </q-item-section>

          <q-item-section side>
            <q-icon name="info" />
          </q-item-section>
        </q-item>

        <q-item to="/posts">
          <q-item-section avatar top>
            <q-avatar icon="list_alt" color="blue" text-color="white" />
          </q-item-section>

          <q-item-section>
            <q-item-label lines="1">Posts</q-item-label>
            <q-item-label caption>Lista de Postagens</q-item-label>
          </q-item-section>

          <q-item-section side>
            <q-icon name="library_music" />
          </q-item-section>
        </q-item>

      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
