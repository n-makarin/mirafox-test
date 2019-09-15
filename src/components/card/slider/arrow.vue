<template>
  <div class="card-slider__arrow">
    <button @click="$emit('left', 'left')" v-if="direction === 'left'">
      <div>&#60;</div>
    </button>
    <button @click="$emit('right', 'right')" v-else>
      <div>&#62;</div>
    </button>
  </div>
</template>

<script>

export default {
  props: {
    direction: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="scss" scoped>
.card-slider__arrow {
  z-index: 2;
  button {
    width: 40px;
    height: 80px;
    border-radius: 3px;
    background: #a0a0a0;
    color: #e4e4e4;
    border: none;
    font-size: 27px;
    cursor: pointer;
    &:hover {
      background: #949494;
    }
    div {
      display: block;
      transform: scale(1, 2.5)
    }
  }
}
</style>
