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
          <div class="card-item-info-top__rating__star">
            <img src="../../assets/icons/star-solid.svg" alt="star">
            <div>{{ parseFloat(data.rating.starNumber) }}</div>
          </div>
          <div class="card-item-info-top__rating__votes">({{ data.rating.votesNumber }})</div>
        </div>
      </div>
      <div class="card-item__info__bottom card-item-info-bottom">
        <div class="card-item-info-bottom__likes" @click="setLike()">
          <img src="../../assets/icons/heart-solid.svg" alt="">
        </div>
        <div class="card-item-info-bottom__cost">от {{ data.cost }}₽</div>
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
  },
  methods: {
    setLike() {
      alert('Лайк товара с id ' + this.data.id)
    }
  }
}
</script>

<style lang="scss" scoped>
.card-item {
  max-width: 225px;
  border: 1px solid #d0d3e2;
  box-sizing: border-box;
  background: white;
  &__img {
    img {
      max-width: 100%;
    }
  }
  &__info {
    padding: 15px 15px 10px 15px;
    &__title {
      margin-bottom: 10px;
    }
  }
  &-info-top {
    display: flex;
    justify-content: space-between;
    padding-bottom: 10px;
    margin-bottom: 10px;
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
        color: #b1b0af;
      }
    }
    &__rating {
      display: flex;
      align-items: center;
      &__star {
        display: flex;
        align-items: center;
        margin-right: 5px;
        font-size: 15px;
        img {
          width: 13px;
          height: 13px;
          margin-right: 5px;
        }
        color: #ffb300;
      }
      &__votes {
        display: inline-block;
        color: #d5d5d5;
        font-size: 14px;
      }
    }
  }
  &-info-bottom {
    display: flex;
    justify-content: space-between;
    align-items: center;
    
    &__likes {
      align-self: center;
      width: 15px;
      height: 15px;
      cursor: pointer;
      opacity: .7;
      &:hover {
        opacity: 1;
      }
      img {
        width: 100%;
      }

    }

    &__cost {
      color: #3d7843;
      font-weight: bold;
    }
  }
}
</style>
