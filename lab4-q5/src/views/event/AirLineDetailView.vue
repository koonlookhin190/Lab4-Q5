<template>
  <h1>Airline ID: {{ airline.id }} {{ airline.AirlineName }}</h1>
  <p>Email: {{ airline.email }} | Address: {{ airline.address }}</p>
  <button @click="editAirline">Edit Airline</button>
</template>
<script>
export default {
  props: ['airline', 'resa', 'passenger'],
  inject: ['GStore'],
  methods: {
    editAirline() {
      this.GStore.flashMessage = 'The airline data has been update '
      setTimeout(() => {
        //After 3 secound remove it
        this.GStore.flashMessage = ''
      }, 5000)
      this.$router.push({
        name: 'PassengerDetailView',
        params: { id: this.passenger.id }
      })
    }
  }
}
</script>
