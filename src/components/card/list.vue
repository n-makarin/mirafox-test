<template>
  <div class="card-list">
    <item 
      class="card-list__item"
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

<style lang="scss" scoped>
.card-list {
  display: flex;
  flex-wrap: wrap;
  &__item {
    margin: 10px;
  }

  /* modifiers */
  &_list-view {
    justify-content: center;
  }
}
</style>
