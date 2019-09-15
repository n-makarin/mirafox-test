<template>
  <div class="card-item">
    <div class="card-item__img">
      <img :src="imgPath" alt="card">
    </div>
    <div class="card-item__info">
      <div class="card-item__info__title">{{ data.title }}</div>
      <div class="card-item__info__top card-item-info-top">
        <div class="card-item-info-top__user">
          <div class="card-item-info-top__user__activity"></div>
          <div class="card-item-info-top__user__name">{{ data.userName }}</div>
        </div>
        <div class="card-item-info-top__rating">
          <div class="card-item-info-top__rating__star">{{ parseFloat(data.rating.starNumber) }}</div>
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
  },
  computed: {
    imgPath() {
      return 'https://picsum.photos/280/200/?random'
    }
  }
}
</script>

<style lang="scss" scoped>
.card-item {
  max-width: 225px;
  border: 1px solid #d0d3e2;
  box-sizing: border-box;
  &__img {
    img {
      max-width: 100%;
    }
  }
  &__info {
    padding: 15px;
    &__title {
      margin-bottom: 10px;
    }
  }
  &-info-top {
    display: flex;
    justify-content: space-between;
    padding-bottom: 10px;
    border-bottom: 1px solid #e7e7e7;
    &__user {
      &__activity {
        display: inline-block;
        width: 10px;
        height: 10px;
        margin-right: 5px;
        background: #e7e7e7;
        border-radius: 50%;
      }
      &__name {
        display: inline-block;
        color: #d2d2d2;
      }
    }
    &__rating {
      &__star {
        display: inline-block;
        color: #ffb300;
      }
      &__votes {
        display: inline-block;
        color: #d5d5d5;
      }
    }
  }
  &-info-bottom {

    &__cost {
      color: #3d7843;
      font-weight: bold;
    }
  }
}
</style>
