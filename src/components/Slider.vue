<template>
  <label class="base">
    <span>{{ label }}</span>

    <input type="range" min="0" max="1" @input="onChange" :value="value" />
  </label>
</template>

<script>
export default {
  props: {
    label: { type: String, default: null },
    value: { type: [String, Number], default: null }
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

  & input {
    width: 55px;
    height: 20px;
    -webkit-appearance: none;
    background: #d3d3d3;
    height: 25px;
    border-radius: 20px;
    padding: var(--padding-xs);

    &::-webkit-slider-thumb {
      -webkit-appearance: none;
      appearance: none;
      width: 25px;
      height: 25px;
      border-radius: 50%;
      background: var(--color-primary);
      cursor: pointer;
      transition: all 0.2s;
    }
  }
}
</style>
