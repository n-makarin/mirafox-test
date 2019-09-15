<template>
  <div class="page-index">
    <card-list :data="cardListData" />
    <card-slider :data="cardListData" />
  </div>
</template>

<script>
import CardList from '@/components/card/list'
import CardSlider from '@/components/card/slider'
import db from '@/db.json'

export default {
  components: {
    CardList,
    CardSlider
  },
  computed: {
    cardListData() {
      return db.cardList
    }
  }
}
</script>

<style scoped>
</style>
