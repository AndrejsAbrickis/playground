<template>
  <button type="button" @click="handleClick">{{ label }}</button>
</template>

<script>
export default {
  name: "ButtonIncrease",
  props: {
    count: Number,
    label: String,
  },
  methods: {
    handleClick() {
      this.$emit("buttonClicked", {
        label: this.label,
        count: this.count++,
      });
    },
  },
};
</script>
