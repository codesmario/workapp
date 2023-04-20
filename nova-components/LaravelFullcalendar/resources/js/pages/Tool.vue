<template>
  <div>
    <Head title="Calendario" />

    <Heading class="mb-6">Calendario</Heading>

  

      <FullCalendar :options="calendarOptions" />

      <h1 class="dark:text-white text-4xl font-light mb-6">
        We're in a black hole.
      </h1>


  
  </div>
</template>

<script>
import FullCalendar from '@fullcalendar/vue3'
import dayGridPlugin from '@fullcalendar/daygrid'
import interactionPlugin from '@fullcalendar/interaction'
export default {
  components: { FullCalendar },
  methods: {
    //
    handleDateClick: function(arg) {
      alert('date click! ' + arg.dateStr)
    }
  },
  data() {
    return {
      calendarOptions: {
        plugins: [ dayGridPlugin, interactionPlugin ],
        initialView: 'dayGridMonth',
        dateClick: this.handleDateClick,
        events: [
          { title: 'event 1', date: '2023-04-01' },
          { title: 'event 2', date: '2023-04-02' }
        ]
      }
    }
  }
}
</script>

<style>
/* Scoped Styles */
</style>
