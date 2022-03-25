<template>
  <q-page class="flex column">
    <q-banner class=" bg-grey-4 text-center">
      User is offline.
    </q-banner>
    <div class="q-pa-md column col justify-end">
      <q-chat-message
        v-for="message in messages"
        :key="message.text"
        :name="message.from"
        :text="[message.text]"
        :sent="message.from == 'me' ? true : false"
      />
    </div>
    <q-footer elevated cen>
      <q-toolbar>
        <q-form @submit="sendMessage"
        class="full-width">
        <q-input class="" bg-color="white" outlined rounded v-model="newMessage" label="Type here" dense>

          <template v-slot:after>
            <q-btn color="white" round dense flat icon="send" />
          </template>
        </q-input>
        </q-form>
      </q-toolbar>
    </q-footer>
  </q-page>
</template>

<script>
export default {
  data() {
    return{
      newMessage: '',
      messages: [
        {
          text: 'oiasndaoisndasiod',
          from: 'me'
        },
        {
          text: 'ioqwnwoiqwndqiwod',
          from: 'Karoline'
        }
      ]
    }
  },
  methods: {
    sendMessage() {
      this.messages.push({
        text: this.newMessage,
        from: 'me'
      })
    }
  }
}
</script>
