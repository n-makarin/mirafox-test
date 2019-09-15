<template>
  <div class="card-slider">
    <arrow direction="left" />
    <card-list class="card-slider__card-list card-list_slider-view" :data="slideData" />
    <arrow direction="right" />
  </div>
</template>

<script>
import CardList from '@/components/card/list'
import Arrow from '@/components/card/slider/arrow'

export default {
  components: {
    CardList,
    Arrow
  },
  props: {
    data: {
      type: Array,
      default: () => []
    }
  },
  computed: {
    slideData() {
      return this.data
    }
  }
}
</script>

<style scoped>
</style>
