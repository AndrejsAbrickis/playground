<template>
  <div id="app">
    <p>Count: {{ count }}</p>
    <div>
      <ButtonDecrease
        :label="labels.decrease"
        :count="count"
        @buttonClicked="handleDecrease"
      />
      <ButtonIncrease
        :label="labels.increase"
        :count="count"
        @buttonClicked="handleIncrease"
      />
    </div>
    <fieldset title="Messages">
      <legend>
        Log Messages
      </legend>
      <p v-for="(message, index) in messages" :key="index">
        {{ message }}
      </p>
    </fieldset>
  </div>
</template>

<script>
import ButtonDecrease from "./ButtonDecrease.vue";
import ButtonIncrease from "./ButtonIncrease.vue";

export default {
  name: "Parent",

  components: {
    ButtonDecrease,
    ButtonIncrease
  },

  data() {
    return {
      labels: {
        decrease: "Decrease",
        increase: "Increase"
      },
      count: 0,
      messages: []
    };
  },

  methods: {
    handleDecrease(message) {
      this.count--;
      this.messages.push(
        `${new Date().getTime()}: "buttonClicked": ${JSON.stringify(message)}`
      );
    },
    handleIncrease(message) {
      this.count++;
      this.messages.push(
        `${new Date().getTime()}: "buttonClicked": ${JSON.stringify(message)}`
      );
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
