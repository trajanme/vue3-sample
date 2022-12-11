<script>
import moment from "moment"

export default {
  name: "MomentSample",
  computed: {
    getTime() {
      return moment().format("YYYY-MM-DD HH:mm:ss");
    }
  }
}
</script>

<template>
  <div class="momentSample">
    <h1>Moment Sample</h1>
    <h3>Current Time</h3>
    <p>{{ getTime }}</p>
  </div>
</template>