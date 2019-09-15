<template>
  <div class="card-slider">
    <card-list class="card-slider__card-list card-list_slider-view" :data="slideData" />
  </div>
</template>

<script>
import CardList from '@/components/card/list'

export default {
  components: {
    CardList
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
