<template>
  <q-layout view="hHh lpR fFf">

    <q-header elevated class="bg-primary text-white" height-hint="98">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="http://assets.stickpng.com/images/5845cd230b2a3b54fdbaecf7.png">
          </q-avatar>
          {{ title }}
        </q-toolbar-title>

        <q-btn
          to="/auth"
          class="absolute-right q-pr-md"
          icon="account_circle"
          no-caps
          flat
          dense
          label="Login"
        />
      </q-toolbar>

      <q-tabs align="left">
        <q-route-tab to="/page1" label="Users" />
        <q-route-tab to="/page2" label="Friends" />
        <q-route-tab to="/page3" label="Rooms" />
      </q-tabs>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  computed: {
    title() {
      let currentPath = this.$route.fullPath
      if (currentPath == '/') return 'PepeChat'
      else if (currentPath == '/chat') return 'Chat'
      else if (currentPath == '/auth') return 'Login'
    }
  },
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
