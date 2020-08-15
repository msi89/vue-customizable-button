<template>
  <button class="button" :style="styles" @mouseover="onMouseOver" @mouseout="onMouseOut">
    <slot/>
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    border: { type: [String, Number], default: 1 },
    borderColor: { type: String, default: "#ccc" },
    color: { type: String, default: "#000" },
    background: { type: String, default: "#eee" },
    disableColor: { type: String, default: "#c9c9c9" },
    disableBackground: { type: String, default: "#eee" },
    mouseOverColor: { type: String, default: "#000" },
    mouseOverBackground: { type: String, default: "#ddd" },
    corner: { type: [String, Number], default: 0 },
    margin: { type: [String, Number], default: 1 },
    padding: { type: [String, Number], default: "5px 15px" },
    width: { type: [String, Number], default: "auto" },
    height: { type: [String, Number], default: "auto" },
    disabled: { type: Boolean, default: false }
  },
  data() {
    return {
      isMouseHover: false
    };
  },
  computed: {
    styles() {
      return {
        borderWidth: this._border,
        borderColor: this.borderColor,
        borderRadius: this._corner,
        color: this._color,
        background: this._background,
        padding: this._padding,
        margin: this._margin,
        width: this._width,
        height: this._height,
        cursor: this._cursor
      };
    },
    _color() {
      if (this.disabled) {
        return this.disableColor;
      }
      return this.isMouseHover ? this.mouseOverColor : this.color;
    },
    _background() {
      if (this.disabled) {
        return this.disableBackground;
      }
      return this.isMouseHover ? this.mouseOverBackground : this.background;
    },
    _border() {
      if (typeof this.border === "number") return `${this.border}px`;
      return this.border;
    },
    _corner() {
      if (typeof this.corner === "number") return `${this.corner}px`;
      return this.corner;
    },
    _margin() {
      if (typeof this.margin === "number") return `${this.margin}px`;
      return this.margin;
    },
    _padding() {
      console.log(typeof this.padding);

      if (typeof this.padding === "number") return `${this.padding}px`;
      return this.padding;
    },
    _width() {
      if (typeof this.padding === "number") return `${this.width}px`;
      return this.width;
    },
    _height() {
      if (typeof this.padding === "number") return `${this.height}px`;
      return this.height;
    },
    _cursor() {
      if (this.disabled) {
        return "default";
      }
      return "pointer";
    }
  },
  methods: {
    onMouseOver() {
      this.isMouseHover = true;
    },
    onMouseOut() {
      this.isMouseHover = false;
    },
    isNumeric(value) {
      return /^\d+$/.test(value);
    }
  }
};
</script>


<style scoped>
.button {
  outline: none;
  border-style: solid;
  transition: all 0.4s ease-in-out;
}
</style>
