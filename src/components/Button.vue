<template>
  <button
    v-on="$listeners"
    class="base"
    :class="{ dark, light, primary, secondary }"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    dark: { type: Boolean, default: true },
    light: { type: Boolean, default: false },
    primary: { type: Boolean, default: false },
    secondary: { type: Boolean, default: false }
  }
};
</script>

<style scoped lang="scss">
.base {
  padding: var(--padding-s);
  font-weight: 600;
  border: none;
  border-radius: var(--border-radius-xs);
  cursor: pointer;

  &:not(:last-child) {
    margin-right: var(--padding-s);
  }
}

.dark {
  color: var(--color-basic-black);
}

.light {
  color: var(--color-basic-white);
}

.primary {
  background-color: var(--color-primary, darkgrey);

  &:hover {
    opacity: 0.8;
  }
}

.secondary {
  background-color: var(--color-secondary, lightgrey);

  &:hover {
    opacity: 0.8;
  }
}
</style>
