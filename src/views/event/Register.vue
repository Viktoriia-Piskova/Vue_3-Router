<template>
  <div v-if="event">
    <p>Register for event here</p>
    <button @click="register">Register me</button>
  </div>
</template>

<script>
export default {
  props: ['event'],
  methods: {
    register() {
      //API call. If success then redirect to event details
      this.$router.push({ name: 'EventDetails', params: { id: this.event.id } })
    }
  }
}
</script>
