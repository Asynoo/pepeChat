<template>
  <q-form @submit="submitForm">
    <q-input
      outlined
      v-model="formData.email"
      class="q-mb-md"
      type="email"
      label="Email" />

    <q-input
      v-if="tab == 'register'"
      outlined
      v-model="formData.name"
      class="q-mb-md"
      label="Name" />

    <q-input
      outlined
      v-model="formData.password"
      class="q-mb-md"
      type="password"
      label="Password" />

    <div class="row">
      <q-space/>
    <q-btn
      color="primary"
      type="submit"
      :label="tab"/>
    </div>
  </q-form>
</template>

<script>
export default {
  props: ['tab'],
  data() {
    return {
      formData: {
        email:'',
        name:'',
        password:''
      }
    }
  },
  methods: {
    submitForm() {
      if (this.tab == 'login') {
        console.log('Login The User')
      }
      else {
        console.log('Register The User')
      }
    }
  }
}
</script>

<style scoped>

</style>
