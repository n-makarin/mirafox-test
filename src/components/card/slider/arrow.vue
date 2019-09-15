<template>
  <div class="card-slider__arrow">
    <button v-if="direction === 'left'">
      <div>&#60;</div>
    </button>
    <button v-else>
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
  button {
    width: 40px;
    height: 100px;
    border-radius: 3px;
    background: #a0a0a0;
    color: #e4e4e4;
    border: none;
    font-size: 27px;
    cursor: pointer;
    div {
      display: block;
      transform: scale(1, 2.5)
    }
  }
}
</style>
