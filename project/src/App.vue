<template>
  <div>
     <!--   @Property('boolean') displayLoadingBubble?: boolean; -->
        <!-- :initialMessages="initialMessages" --> 
    <h1>Deep Chat</h1>
    <deep-chat
      v-bind:demo="{ displayLoadingBubble: true }" 
      v-bind:textInput="{ placeholder: { text: 'Type anything here!' } }"
    />
  </div>
</template>


<script>
import 'deep-chat';

export default {
  name: 'App',
  data() {
    return {
      initialMessages: [
        { role: 'user', text: 'Hey, how are you today?' },
        { role: 'ai', text: 'I am doing very well!' },
      ],
    };
  },
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