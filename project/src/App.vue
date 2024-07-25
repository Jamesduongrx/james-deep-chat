<template>
  <div>
    <!--   @Property('boolean') displayLoadingBubble?: boolean; -->
        <!-- :initialMessages="initialMessages" --> 
    <h1>Deep Chat</h1>
    <deep-chat
      :demo="{displayLoadingBubble}"
      :onNewMessage="NewMessageResponse"
      :initialMessages="initialMessages"
      :displayLoadingBubble="displayLoadingBubble"
      v-bind:textInput="{ placeholder: { text: 'Type anything here!' } }"
    />
    <button @click="toggle()">Toggle Bubble</button>
  </div>
</template>

<script>
import "deep-chat";

export default {
  name: 'App',
  data() {
    return {
      initialMessages: [

      ],
      displayLoadingBubble: true,
    };
  },
  methods: {
    NewMessageResponse(message) {
      if (!message.detail.isInitial) {
        this.initialMessages.push(message.detail.message);
      }
    },
    toggle: function() {
      this.displayLoadingBubble = !this.displayLoadingBubble;
    }
  }
};
</script>

<style>
div {
  font-family: sans-serif;
  text-align: center;
  justify-content: center;
  display: grid;
}
</style>

















