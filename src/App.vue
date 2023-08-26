<template>
  <div id="app">
    <!-- Create new ref by setting "ref" prop -->
    <input
      type="text"
      placeholder="Text"
      ref="inputField"
    />
    <button @click="sendMessage">Shout</button>
    <br />
    <b>{{ shout }}</b>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      shout: '',
    };
  },
  methods: {
    sendMessage() {
      const message = this.$refs.inputField.value;
      axios
        .post("http://localhost:8000/message/")
      this.shout = `${message.toUpperCase()}!!!`;
    },
  },
};
</script>