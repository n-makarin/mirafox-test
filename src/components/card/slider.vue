<template>
  <div class="card-slider">
    <arrow @left="turnLeft" direction="left" />
    <card-list class="card-slider__card-list card-list_slider-view" :data="slideData" />
    <arrow @right="turnRight" direction="right" />
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
  data: () => ({
    itemsToShow: 5,
    itemsToLoad: 5,
    slideNumber: 1
  }),
  computed: {
    slideData() {
      if (this.slideNumber >= 0) {
        return this.data.slice(this.startItemNumber, this.endItemNumber)
      } else {
        return this.data.slice(this.endItemNumber, this.startItemNumber)
      }
    },
    /**
     * All slides quantity
     */
    allSlidesNumber() {
      return this.data.length / this.itemsToLoad
    },
    /**
     * Start number to slicing from data array
     */
    startItemNumber() {
      return this.slideNumber * this.itemsToLoad - this.itemsToLoad
    },
    /**
     * End number to slicing from data array
     */
    endItemNumber() {
      return this.startItemNumber + this.itemsToShow
    }
  },
  methods: {
    turnLeft() {
      if (this.slideNumber - 1 >= 1) {
        this.slideNumber--
      } else {
        this.slideNumber = this.allSlidesNumber
      }
    },
    turnRight() {
      if (this.slideNumber + 1 <= this.allSlidesNumber) {
        this.slideNumber++
      } else {
        this.slideNumber = 1
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.card-slider {
  display: flex;
  align-items: center;
  overflow: hidden;
}
</style>
