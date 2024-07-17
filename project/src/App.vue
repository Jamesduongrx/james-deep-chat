<template>
  <div>
     <!--   @Property('boolean') displayLoadingBubble?: boolean; -->
        <!-- :initialMessages="initialMessages" --> 
    <h1>Deep Chat</h1>
    <deep-chat
      :demo="{displayLoadingBubble}"
      v-bind:textInput="{ placeholder: { text: 'Type anything here!' } }"
      />
      <button @click="toggle()">Toggle Bubble</button>
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
      displayLoadingBubble: true,
    };
  },
  methods:{
        toggle: function() {
          this.displayLoadingBubble = !this.displayLoadingBubble
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