<template>
  <div class="page-index">
    <section>
      <h2>Список карточек</h2>
      <card-list class="page-index__card-list card-list_list-view" :data="cardListData" />
    </section>
    <section>
      <h2>Слайдер карточек</h2>
      <card-slider class="page-index__card-slider" :data="cardListData" />
    </section>
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

<style lang="scss" scoped>
.page-index {
  background: #f5f5f5;
  padding: 50px;
  h2 {
    text-align: center;
    font-weight: normal;
  }
  &__card-list {
    max-width: 1240px;
    margin: 0 auto;
  }
}
</style>
