<template>
  <button type="button" @click="handleClick">{{ label }}</button>
</template>

<script>
export default {
  name: "ButtonIncrease",
  props: {
    label: String
  },
  methods: {
    handleClick() {
      this.$emit("buttonClicked", this.label);
    }
  }
};
</script>
