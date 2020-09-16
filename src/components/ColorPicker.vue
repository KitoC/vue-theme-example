<template>
  <label class="base">
    <span>{{ label }}</span>

    <input type="color" @input="onChange" :value="value" />
  </label>
</template>

<script>
export default {
  props: {
    label: { type: String, default: null },
    value: { type: String, default: null }
  },
  methods: {
    onChange(e) {
      this.$emit("input", e.target.value);
    }
  }
};
</script>

<style scoped lang="scss">
.base {
  display: flex;
  align-items: center;
  padding-bottom: var(--padding-m);

  span {
    margin-right: var(--margin-s);
    color: var(--color-text);
  }
}
</style>
