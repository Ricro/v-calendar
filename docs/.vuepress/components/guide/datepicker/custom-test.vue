<template>
  <div>
    <p>test</p>
    <v-date-picker
      ref="datepicker"
      v-model='selectedDate'
      is-range
      is-expanded
      color="orange"
      :columns="2"
      :rows="1"
      :popover="{
        visibility: 'visible',
      }"
      :locale="{
        masks: {
          weekdays: 'WWW'
        }
      }"
      :disabled-dates="disabledDates"
    />
  </div>
</template>

<script>
/* eslint-disable */

export default {
  data () {
    return {
      selectedDate: {
        start: null,
        end: null
      }
    }
  },
  computed: {

    disabledDates () {
      return ["2020-12-17", "2020-12-18"]
      // if (this.isDragging) {
      //   let availableDates = this.getAvailableDates()
      //   console.log(availableDates)
      //   return Object.keys(this.allDates).filter(e => !availableDates.includes(e))
      // } else {
      //   return Object.keys(this.allDates).filter(e => this.allDates[e] !== true)
      // }
    },
  },
  methods: {

  },
  created () {
    // this.getPricesAvailibility()
  }

}
</script>

<style>

</style>