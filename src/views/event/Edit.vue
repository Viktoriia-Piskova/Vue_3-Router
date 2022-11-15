<template>
  <div v-if="event">
    <p>Register for event here</p>
  </div>
</template>

<script>
export default {
  props: ['event'],
  data() {
    return {
      unsavedChanges: true
    }
  },
  beforeRouteLeave() {
    if (this.unsavedChanges) {
      const answer = window.confirm(
        'Do you really want to leave? You have unsaved changes'
      )
      if (!answer) {
        return false
      }
    }
  }
}
</script>
