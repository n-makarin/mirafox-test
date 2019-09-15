<template>
  <div class="page-index">
    <card-list />
    <card-slider />
  </div>
</template>

<script>
import CardList from '@/components/card/list'
import CardSlider from '@/components/card/slider'

export default {
  components: {
    CardList,
    CardSlider
  },
  props: {
  }
}
</script>

<style scoped>
</style>
