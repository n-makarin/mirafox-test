<template>
  <div class="card-list">
    <item 
      v-for="(item, index) in data" 
      :key="index"
      :data="item"
    />
  </div>
</template>

<script>
import Item from '@/components/card/item'

export default {
  components: {
    Item
  },
  props: {
    data: {
      type: Array,
      default: () => []
    }
  }
}
</script>

<style scoped>
</style>
