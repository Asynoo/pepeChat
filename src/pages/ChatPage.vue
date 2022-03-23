<template>
  <q-page class="flex flex-center">
    <q-footer elevated cen>
      <q-toolbar>
        <q-input class="absolute-center" bg-color="white" outlined rounded v-model="text" label="Type here" dense>

          <template v-slot:after>
            <q-btn color="white" round dense flat icon="send" />
          </template>
        </q-input>
      </q-toolbar>
    </q-footer>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage'
})
</script>
