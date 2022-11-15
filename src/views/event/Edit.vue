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
  beforeRouteLeave(routeTo, routeFrom, next) {
    if (this.unsavedChanges) {
      const answer = window.confirm(
        'Do you really want to leave? You have unsaved changes'
      )
      if (answer) {
        next()
      } else {
        next(false)
      }
    } else {
      next()
    }
  }
}
</script>
