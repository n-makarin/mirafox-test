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
    slideNumber: 1,
    windowWidth: 0,
    screenTypes: {
      lg: 1320,
      md: 960,
      sm: 720,
      xs: 540
    }
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
  mounted: function () {
    this.$nextTick(function () {
      window.addEventListener('resize', this.setSlidesNumber);
    })
  },
  methods: {
    setSlidesNumber() {
      const windowWidth = window.innerWidth
      if (windowWidth >= this.screenTypes.lg) {
        this.itemsToShow = 5
      } else if (windowWidth >= this.screenTypes.md) {
        this.itemsToShow = 3
      } else if (windowWidth >= this.screenTypes.sm) {
        this.itemsToShow = 2
      } else {
        this.itemsToShow = 1
      }
    },
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
  justify-content: center;
  overflow: hidden;
}
</style>
