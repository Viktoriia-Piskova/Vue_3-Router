<template>
  <div v-if="event">
    <p>Register for event here</p>
    <button @click="register">Register me</button>
  </div>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore'],
  methods: {
    register() {
      //API call. If success then redirect to event details
      this.GStore.flashMessage =
        'You are successfully registered at ' + this.event.title
      setTimeout(() => {
        this.GStore.flashMessage = ''
      }, 3000)
      this.$router.push({ name: 'EventDetails' })
    }
  }
}
</script>
