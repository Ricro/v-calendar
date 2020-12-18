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
      :attributes="attrs"
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
    attrs () {
      return [{
        key: 1,
        highlight: {
          contentClass: 'semi-open',
          class: 'semi-open-class',
        },
        popover: {
          customData: {
            text: `Départ uniquement`
          },
          visibility: 'hover'
        },
        dates: ["2020-12-17", "2020-12-16", "2020-12-26", "2020-12-27"]
      }]
    },

    disabledDates () {
      return ["2020-12-17", "2020-12-16", "2020-12-19", "2020-12-20", "2020-12-26", "2020-12-27"]
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