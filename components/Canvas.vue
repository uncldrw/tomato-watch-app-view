<template>
  <div ref="theCanvas" class="canvas">
    <div class="canvas__content noselect">
      <svg height="100" width="100">
        <circle
          cx="50"
          cy="50"
          r="40"
          stroke="black"
          stroke-width="3"
          fill="red"
        />
      </svg>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    this.mount()
  },
  methods: {
    mount() {
      const dimensionX = this.$refs.theCanvas.scrollHeight
      const dimensionY = this.$refs.theCanvas.scrollWidth
      const sbHeight = this.$refs.theCanvas.offsetHeight / 2
      const sbWidth = this.$refs.theCanvas.offsetWidth / 2

      // eslint-disable-next-line no-console
      console.log(sbHeight)
      this.$refs.theCanvas.scrollTop = dimensionX / 2 - sbHeight
      this.$refs.theCanvas.scrollLeft = dimensionY / 2 - sbWidth
    },
  },
}
</script>

<style lang="scss" scoped>
.canvas {
  position: absolute;
  height: 290px;
  width: 240px;
  background-color: #fff;
  transform: translateX(-9px) translateY(13px);
  border-radius: 10px;
  overflow: auto;
  &::-webkit-scrollbar {
    display: none;
  }
  li {
    color: white;
    font-size: 30px;
  }
}

.canvas__content {
  height: 1000px;
  width: 1000px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.noselect {
  -webkit-touch-callout: none; /* iOS Safari */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Old versions of Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
  user-select: none; /* Non-prefixed version, currently
  supported by Chrome, Edge, Opera and Firefox */
}
</style>
