<template>
  <div class="flex-center flex-column fit-parent" :style="theme">
    <Slider v-model="themeType" label="Dark/Light theme" />

    <div class="flex-column" style="{ 'margin-bottom': '1em' }">
      <ColorPicker v-model="primaryColor" label="Primary Color" />
      <ColorPicker v-model="secondaryColor" label="Secondary Color" />
    </div>

    <div>
      <Button primary light>Primary</Button>
      <Button>Secondary</Button>
    </div>
  </div>
</template>

<script>
import Button from "./components/Button";
import ColorPicker from "./components/ColorPicker";
import Slider from "./components/Slider";

export default {
  components: { Button, ColorPicker, Slider },
  computed: {
    theme() {
      const { themeType, primaryColor, secondaryColor } = this;

      const lightTheme = {
        "--color-text": "#444444",
        background: "white"
      };

      const darkTheme = {
        "--color-text": "white",
        background: "#444444"
      };

      let style = {
        "--color-primary": primaryColor,
        "--color-secondary": secondaryColor
      };

      if (themeType == 0) {
        style = { ...style, ...lightTheme };
      } else {
        style = { ...style, ...darkTheme };
      }

      return style;
    }
  },
  data() {
    return { themeType: 0, primaryColor: "#2d61c2", secondaryColor: "#dad9d9" };
  }
};
</script>

<style lang="scss">
@import "./assets/css/index.scss";
</style>
