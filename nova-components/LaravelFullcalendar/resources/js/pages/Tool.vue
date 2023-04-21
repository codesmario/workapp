<template>
  <div>
    <Head title="Calendario" />

    <Heading class="mb-6">Calendario</Heading>

      <FullCalendar :options="calendarOptions" />
  
  </div>
</template>

<script>
import FullCalendar from '@fullcalendar/vue3'
import dayGridPlugin from '@fullcalendar/daygrid'
import interactionPlugin from '@fullcalendar/interaction'
export default {
  components: { FullCalendar },
  data: () => ({
    calendarOptions: {
      plugins: [ dayGridPlugin, interactionPlugin ],
      initialView: 'dayGridMonth',
      events: []
    }
  }),
  methods: {
    //
    async getEvents() {
      let usersArray = []
      const response =  await fetch('/nova-vendor/laravel-fullcalendar/users')
      const users = await response.json()
      for (const user of users) {
        usersArray.push({
          title: user.name,
          date: user.created_at
        })
      }
      this.calendarOptions.events = usersArray
    }
  },
  async created() {
    await this.getEvents();
  }
}
</script>

<style>
/* Scoped Styles */
</style>
