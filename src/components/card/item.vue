<template>
  <div class="card-item">
    <div class="card-item__img"></div>
    <div class="card-item__title">{{ data.title }}</div>
    <div class="card-item__info">
      <div class="card-item__info__top card-item-info-top">
        <div class="card-item-info-top__user-name">{{ data.userName }}</div>
        <div class="card-item-info-top__rating">
          <div class="card-item-info-top__rating__star">{{ data.rating.starNumber }}</div>
          <div class="card-item-info-top__rating__votes">{{ data.rating.votesNumber }}</div>
        </div>
      </div>
      <div class="card-item__info__bottom card-item-info-bottom">
        <div class="card-item-info-bottom__likes"></div>
        <div class="card-item-info-bottom__cost">{{ data.cost }}</div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  components: {
  },
  props: {
    data: {
      type: Object,
      default: () => {}
    }
  }
}
</script>

<style scoped>
</style>
